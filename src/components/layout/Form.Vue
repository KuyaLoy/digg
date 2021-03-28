<template>
     <form>

            <div class="progress-bar-cont">
                <img class="logo" :src="logo[0].src" alt="" v-if="this.step == 1">
                <img class="logo" :src="logo[1].src" alt="" v-if="this.step != 1">

                <div class="progress" alt="" v-if="this.step != 1">
                    <div class="progress-bar" :style="{width: progressWidth+'%'}"></div>
                </div>
            </div>
            
            <section v-if="step == 1">
                <button v-if="step == 1" @click.prevent="nextStep">apply</button>
            </section>
            <section v-if="step == 2">
                <button @click.prevent="backStep">back</button>
                <button @click.prevent="nextStep">next</button>
            </section>
            <section v-if="step == 3">
                <button @click.prevent="backStep">back</button>
                <button @click.prevent="nextStep">next</button>
            </section>
            <section v-if="step == 4">
                <button @click.prevent="backStep">back</button>
                <button @click.prevent="nextStep">next</button>
            </section>
            <section v-if="step == 5">
                <button @click.prevent="backStep">back</button>
                <button @click.prevent="completedStep">complete application</button>
            </section>

        </form>
</template>

<script>
    export default {
        name: "form"
    }
</script>