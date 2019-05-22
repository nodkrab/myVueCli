<script>
import Counter from "./components/Counter";
import UserList from "./components/UserList";
import AppBar from "./components/AppBar";

export default {
  components: {
    counter: Counter,
    "user-list": UserList,
    appbar: AppBar
  }
};
</script>

<template>
    <div>
        <section class="section">
            <div class="container">
                <!-- <counter/> -->
                <!-- <user-list/> -->
                <appbar/>
                <router-view/>
            </div>
        </section>
    </div>
</template>




