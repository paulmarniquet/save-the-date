<template>
    <div class="myFooter">
        <div class="countdown">
            <h1>{{ countdownText }}</h1>
            <p>DAYS HOURS MINUTES SECONDS</p>
        </div>
        <hr>
        <div class="circles">
            <div class="circle" style="background-color: rgba(255, 251, 150, 0.3)"></div>
            <div class="circle" style="background-color: rgba(255, 219, 150, 0.4)"></div>
            <div class="circle" style="background-color: rgba(255, 177, 150, 0.5)"></div>
            <div class="circle" style="background-color: rgba(255, 153, 150, 0.6)"></div>
            <div class="circle" style="background-color: rgba(253, 26, 19, 0.5)"></div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'myFooter',
    data() {
        return {
            countdownText: '',
            countDownDate: new Date("Oct 28, 2024 00:00:00").getTime()
        }
    },
    mounted() {
        setInterval(() => {
            const now = new Date().getTime();
            const timeleft = this.countDownDate - now;
            const days = Math.floor(timeleft / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeleft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeleft % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeleft % (1000 * 60)) / 1000);
            this.countdownText = `${days} ${hours} ${minutes} ${seconds}`;
        }, 1000);
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.myFooter {
    margin-top: 300px;
    position: relative;
    width: 100%;
    height: auto;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.countdown {
    width: 100%;
    height: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.countdown p {
    font-size: 20px;
    font-family: "Roboto Thin", sans-serif;
    letter-spacing: 2px;
    color: rgb(0, 0, 0, 0.6);
    margin: 0;
}

.countdown h1 {
    font-size: 20px;
    font-family: "Roboto Regular", sans-serif;
    margin: 0;
}

.circles {
    position: relative;
    width: 50%;
    height: auto;
    margin: 12% auto;
    display: flex;
    justify-content: center;
    align-items: center;
}

hr {
    width: 70%;
    position: relative;
    margin-top: 5%;
    margin-bottom: 1%;
}

.circles {
    margin-top: 1%;
    margin-bottom: 4%;
}

.circle {
    margin: 1%;
    width: 20px;
    height: 20px;
    border-radius: 50%;
}

@media (max-width: 415px) {
    .myFooter {
        margin-top: 100px;
    }

    .countdown h1 {
        font-size: 14px;
    }

    .countdown p {
        font-size: 14px;
        letter-spacing: 1px;
    }

    .circle {
        margin: 1%;
        width: 10px;
        height: 10px;
    }
}

</style>
