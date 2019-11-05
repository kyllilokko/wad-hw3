<template>
    <div>
        <button id="add-course-button" class="blue-button" @click="selected=!selected">+</button>
        <span id="add-course" v-show="selected">
            <input class="input" type="text" placeholder="Course title" id="title" v-model="course">
            <input class="input" type="number" min="1" max="8" placeholder="Semester" id="semester" v-model="semester">
            <input class="input" type="number" min="0" max="100" placeholder="Grade" id="grade" v-model="grade">
            <button class="green-button" id="save-course" @click="hideAndAddCourse">Save</button>
            <button class="grey-button" id="cancel-course" @click="clearAddCourse">Cancel</button>
        </span>
    </div>
</template>

<script>
    export default {
        name: "AddCourse",
        data: () => {
            return {
                selected: false,
                course: '',
                semester: Number,
                grade: Number
            }
        },
        methods: {
            clearAddCourse: function () {
                this.selected = false;
                this.course = '';
                this.semester = '';
                this.grade = ''

            },
            hideAndAddCourse: function () {
                this.addCourse(this.course, this.semester, this.grade);
                this.clearAddCourse()
            }
        },
        props: {
            addCourse: Function
        }
    }
</script>

<style scoped>

</style>