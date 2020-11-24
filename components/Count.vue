<template>
    <div>
        <p v-bind:style="p" v-on:mouseover="overMessage" v-bind:title="texto" class="counter">{{ clock.hour }} <code>Horas</code> {{ clock.minuts }} <code>Minutos</code> {{ clock.seconds }} <code>Segundos</code></p>
    </div>
</template>

<script>
export default {

    data() {
        return {
            clock: {
                hour: 0,
                minuts: 0,
                seconds: 0
            },
            
            p: {
                fontSize: 2 + 'rem'
            },

            texto: "Agora é ",
        }
    },

    mounted() {
        setInterval(()=>{
            this.clock.seconds++
            if (this.clock.seconds >= 60) {
                this.clock.seconds = 0
                this.clock.minuts++
            }
            if (this.clock.minuts >= 60) {
                    this.clock.minuts = 0
                    this.clock.hour++
            }
            if (this.clock.hour > 23){
                this.clock.hour = 0
            }
        }, 1000)
    },

    methods: {
        overMessage() {
            this.texto = ''
            this.texto = this.texto + new Date().toLocaleString()
        }
    }

}
</script>