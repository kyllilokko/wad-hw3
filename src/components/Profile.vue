<template>
    <div id="profile-container" class="tab active">
        <div id="profile">
            <div class="avatar">
                <img src="../assets/me.png" id="picture" alt="My picture">
            </div>
            <div class="info">
                <ul>
                    <li id="name">John Doe</li>
                    <li id="birthdate">11/10/1990</li>
                    <li id="faculty">Software Engineering</li>
                </ul>
            </div>
            <div id="gpa">
                <strong><CalculateGPA/></strong>
            </div>
            <div class="clear-fix"></div>
        </div>
    </div>
</template>

<script>

    import CalculateGPA from "./CalculateGPA";

    export default {
        name: "Profile",
        components: {CalculateGPA},
    }
</script>

<style>



</style>

