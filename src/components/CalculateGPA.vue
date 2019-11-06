<template>
    <div>
        {{Math.round(gpa * 100) / 100}}
    </div>
</template>

<script>

    import {EventBus} from '../eventBus.js';
    export default {
        name: "CalculateGPA",
        data: () => {
            return { gpa : -99

            }
        },
        methods: {
        calculateGPA (courses) {
            let sum = 0;
            for (let i = 0; i < courses.length; i++) {
                let grade = courses[i].grade;
                if (grade > 90) {
                    sum += 4;
                } else if (grade > 80) {
                    sum += 3;
                } else if (grade > 70) {
                    sum += 2;
                } else if (grade > 60) {
                    sum += 1;
                } else if (grade > 50) {
                    sum += 0.5;
                } else sum += 0;
            }
            return sum/courses.length;
        }
        },
        created() {
            EventBus.$on('update-gpa', (courses) => {
                this.gpa = this.calculateGPA(courses);
            });
        }

    }
</script>

<style scoped>

</style>