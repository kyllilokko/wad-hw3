<template>
    <div id="courses-container" class="tab active">
        <h1 class="title">Courses</h1>
        <table id="courses">
            <thead>
            <tr>
                <th>#</th>
                <th>Course Title</th>
                <th>Semester</th>
                <th>Grade</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="(item, index) in courses" :key="index" @click="addCourse">
                <td>{{index+1}}</td>
                <td>{{item.course}}</td>
                <td>{{item.semester}}</td>
                <td>{{item.grade}}</td>
            </tr>

            </tbody>
        </table>
        <br>
        <br>
        <AddCourse :add-course="addCourse"/>
    </div>
</template>

<script>
    import AddCourse from "./AddCourse";
    import {EventBus} from '../eventBus.js';
    export default {
        name: "Courses",
        components: {AddCourse},
        data: () => {
            return {
                courses: [
                    {
                        course: 'Agile software development',
                        semester: 1,
                        grade: 82
                    },
                    {
                        course: 'System modelling',
                        semester: 1,
                        grade: 85
                    }, {
                        course: 'Object-oriented programming',
                        semester: 2,
                        grade: 99
                    }, {
                        course: 'Estonian language Level A2',
                        semester: 2,
                        grade: 65
                    }]
            }
        },
        methods: {
            addCourse: function (course, semester, grade) {
                this.courses.push({course: course, semester: semester , grade: grade});
                EventBus.$emit('update-gpa', this.courses);
            }
        },
        created() {
            EventBus.$emit('update-gpa', this.courses);
        }
    }
</script>

<style scoped>

</style>