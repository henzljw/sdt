<template>
    <v-container fill-height fluid>
        <v-row class="text-center" align="center" justify="center">
            <v-col>
                <div v-show="showTime" class="time">
                    {{ showTime.hours }}:{{ showTime.minutes }}:{{ showTime.seconds }}
                </div>
                <div v-show="showDate" class="date">
                    {{ showDate.days }} - {{ showDate.months }} - {{ showDate.years }}
                </div>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
const currentDateTime = new Date();

export default {
    name: 'DateTime',

    data() {
        return {
            showTime: {
                hours: (currentDateTime.getHours() < 10 ? '0' : '') + currentDateTime.getHours(),
                minutes: (currentDateTime.getMinutes() < 10 ? '0' : '') + currentDateTime.getMinutes(),
                seconds: (currentDateTime.getSeconds() < 10 ? '0' : '') + currentDateTime.getSeconds(),
            },
            showDate: {
                days: currentDateTime.getDate(),
                months: currentDateTime.toLocaleString("en-us", { month: 'short' }),
                years: currentDateTime.getFullYear(),
            },
            timer: undefined,
        };
    },

    methods: {
        showCurrentDateTime() {
            const currentDateTime = new Date();
            this.showTime = {
                hours: (currentDateTime.getHours() < 10 ? '0' : '') + currentDateTime.getHours(),
                minutes: (currentDateTime.getMinutes() < 10 ? '0' : '') + currentDateTime.getMinutes(),
                seconds: (currentDateTime.getSeconds() < 10 ? '0' : '') + currentDateTime.getSeconds(),
            }
            this.showDate = {
                days: currentDateTime.getDate(),
                months: currentDateTime.toLocaleString("en-us", { month: 'short' }),
                years: currentDateTime.getFullYear(),
            }
        },
    },
    beforeMount() {
        this.timer = setInterval(this.showCurrentDateTime, 1000);
    },
    beforeUnmount() {
        clearInterval(this.timer);
    },
};
</script>
  
<style>
.text-center {
    transform: translateY(-10%);
}

.time {
    font-size: 120px;
}

.date {
    font-size: 30px;
}
</style>