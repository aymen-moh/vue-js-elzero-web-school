<template>
    <div class="post-box">
        <div class="row">
            <div class="col-sm-12">
                <span class="post-views">{{ views }}</span>
                <h3 class="post-title" v-bold v-font="60">{{ title | uppercase }}</h3>
                <span class="post-date">{{ date }}</span>
                <p class="post-content">{{ content | shorten(20, " ...") | reverse }}</p>
                <div class="row">
                    <div class="col-sm-6">
                        <span class="post-author">{{ author | lowercase }}</span>
                    </div>
                    <div class="col-sm-6">
                        <span>{{ category }}</span>
                    </div>
                </div>
            </div>
        </div>
        <br>
        <hr>
    </div>
</template>

<script>
export default {
    name: "Post",
    props: [
        "views", "title", "date", "content", "author", "category"
    ],
    filters:{ // local filter
        lowercase: function(v){
            return v.toLowerCase();
        },
    }
};
</script>
