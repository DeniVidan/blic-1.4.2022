<template>
    <div class="data">
        <div class="card">
            <p>Author: {{ authors }}</p>
            <p>Name: {{ name  }}</p>
            <p>Released: {{ released }}</p>

        </div>
    </div>
</template>

<script>
export default {
    name: "authors",
    props: {
        authors: String,
        name: String,
        released: String
    }
}

</script>

<style>

</style>