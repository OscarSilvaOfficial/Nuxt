<template>
    <div class="posts">
        <form id="form-comment">
            <input class="input" type="text" v-model="pessoa" placeholder="Pessoa">
            <textarea class="textarea" v-model="comentario" placeholder="Comentário"></textarea>
        </form>
        <button class="button is-success is-rounded" form="form-comment">Rounded</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            post: {
                pessoa: [],
                comentario: []
            }
        }
    },

    methods: {
        setComent() {
            console.log(this.post)
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
.is-success {
    margin-top: 1rem;
}
</style>