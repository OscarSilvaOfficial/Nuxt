<template>
    <div class="posts">
        <form id="form-comment">
            <input class="input" type="text" v-model="posts.pessoa" placeholder="Pessoa">
            <input class="input" type="text" v-model="posts.twitter" placeholder="@">
            <input class="input" type="text" v-model="posts.avatar" placeholder="URL da Foto">
            <input class="input" type="text" v-model="posts.tags" placeholder="Tag">
            <textarea class="textarea" v-model="posts.comentario" placeholder="Comentário"></textarea>
        </form>
        <button class="button is-success is-rounded" v-on:click.prevent="setComent" type="submit" form="form-comment">Rounded</button>
        <hr/>
        <div class="card" v-for="post in posts" :key="post.pessoa" v-if="post.pessoa!= null">
            <div class="card-image">
                <figure class="image is-4by3">
                <img v-bind:src="post.avatar" alt="Placeholder image">
                </figure>
            </div>
            <div class="card-content">
                <div class="media">
                    <div class="media-left">
                        <figure class="image is-48x48">
                        <img v-bind:src="post.avatar" alt="Placeholder image">
                        </figure>
                    </div>
                        <div class="media-content">
                            <p class="title is-4">{{post.pessoa}}</p>
                            <p class="subtitle is-6">@{{post.twitter}}</p>
                        </div>
                    </div>

                    <div class="content">
                        {{ post.comentario }}
                        <a href="#">#{{post.tags}}</a>
                        <br>
                        <time datetime="2016-1-1">11:09 PM - 1 Jan 2016</time>
                    </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            posts: 
            [{

            }]
        }
    },

    methods: {
        setComent() {
            this.posts.push({
                pessoa: this.posts.pessoa,
                comentario: this.posts.comentario
            })
            console.log(this.posts)
        }
    },
}
</script>

<style>
.posts {
    width: 77%;
    margin: 2rem auto 2rem auto;
}
.input {
    margin-bottom: 1rem;
}
.is-success, .card {
    margin: 1rem auto 1rem auto;
}
</style>