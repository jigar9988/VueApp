<script setup>

</script>

<template>
    <div>
        <h1 class="contact">Contact Us</h1>
        <form action="#/" class="d-flex flex-column" id=form method="post">
            <input type="text" placeholder="Enter Your Name">
            <input type="email" placeholder="Enter Your email">
            <input type="tel" placeholder="Enter Your Number">
            <input type="textarea" placeholder="Enter Your concern">
            <button class="btn btn-primary">Submit</button>
        </form>
    </div>
</template>

<style>
.contact{
    text-align: center;
}
#form{
    margin: auto;
    align-items: center;
    justify-content: center;
}
#form input{
    width: 60vw;
    border: 1px solid black;
    border-radius: 4px;
    margin: 4px;
}
</style>