<template>
    <p>You catch it in ( {{score}} ) milisecond.</p>

    <div v-if="score<250">
        <p>Ooh ! you have fast hand dude!</p>
    </div>

    <div v-else-if="score>250 && score<500">
        <p>Dude ! you are normal Zzz</p>
    </div>

    <div v-else>
        <p>Loser too slow dude!</p>
    </div>
</template>

<script>
export default {
 props:["score"]
}
</script>

<style>
    p{
        text-align: center;
        font-size: 1em;
        font-weight: bold;
        color: #2D8E87;
    }
</style>