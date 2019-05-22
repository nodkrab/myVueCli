<template>
    <div>
        <div class="column">
            <div class="box">
                <h3>Welcome</h3>
                <p>Selected user {{selectuser}} </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: ["selectuser"],
  computed: {}
};
</script>

<style>
</style>
