<template>



    <div>
        <p class="counter">{{ hour }} <code>Horas</code> {{ minuts }} <code>Minutos</code> {{ seconds }} <code>Segundos</code></p>
    </div>
  
</template>

<script>
export default {

    data() {
        return {
            hour: 0,
            minuts: 0,
            seconds: 0
        }
    },

    mounted() {
        setInterval(()=>{
            this.seconds++
            if (this.seconds >= 60) {
                this.seconds = 0
                this.minuts++
            }
            if (this.minuts >= 60) {
                    this.minuts = 0
                    this.hour++
            }
            if (this.hour > 23){
                this.hour = 0
            }
        }, 1000)
    } 

}
</script>

<style>

p.counter {
    font-size: 3rem;
}

</style>