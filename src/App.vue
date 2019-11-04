<template>
    <main id="app">
        <header>
            <strong>Welcome to your dashboard!</strong>
        </header>
        <section id="container">
            <section id="main">
                <div class="content">
                    <Profile/>

                </div>
                <div class="controls">
                    <button id="profile-button" class="pill active">Profile</button>
                    <button id="courses-button" class="pill">Courses</button>
                </div>
            </section>
        </section>
        <footer>
            <ul class="links">
                <li>
                    <a href="https://ois2.ut.ee/" target="_blank">OIS</a>
                </li>
                <li>
                    <a href="https://courses.cs.ut.ee/" target="_blank">Courses</a>
                </li>
            </ul>
        </footer>
    </main>
</template>

<script>

    import Profile from "./components/Profile";

    export default {
        name: 'app',
        components: {
            Profile
        }
    }
</script>


