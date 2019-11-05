<template>
    <div>
        <button id="add-course-button" class="blue-button" @click="selected=!selected">+</button>
        <span id="add-course" v-show="selected">
            <input class="input" type="text" placeholder="Course title" id="title" v-model="course">
            <input class="input" type="number" min="1" max="8" placeholder="Semester" id="semester" v-model="semester">
            <input class="input" type="number" min="0" max="100" placeholder="Grade" id="grade" v-model="grade">
            <button class="green-button" id="save-course">Save</button>
            <button class="grey-button" id="cancel-course" @click="hideAddCourse">Cancel</button>
        </span>
    </div>
</template>

<script>
    export default {
        name: "AddCourse",
        data: () => {
            return {
                selected: false,
                course: String,
                semester: Number,
                grade: Number
            }
        },
        methods: {
            hideAddCourse: function () {
                this.selected = false;
                this.course='';
                this.semester='';
                this.grade=''

            }
        }
    }
</script>

<style scoped>

</style>