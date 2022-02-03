<template>
    <div class="main-container">
        <Navbar />
        
        <!-- <div id="curEl"></div> -->
        <Nuxt />
    </div>
</template>
<style lang="scss" scoped>
    // TODO: Custom Cursor

    // #curEl {
    //     position: absolute;
    //     height: 1.25rem;
    //     width: 1.25rem;
    //     border: 2px solid rgb(223, 223, 233);
    //     border-radius: 100%;
    //     z-index: 999999;
    // }
</style>

<script>
// export default {
//     mounted() {
//         const curEl = document.querySelector('#curEl');
//         let trackMouse = () => {
//             curEl.style.top = e.pageY + 'px';
//             curEl.style.left = e.pageX + 'px';
//             window.requestAnimationFrame(trackMouse);
//         }
//         trackMouse();
//     },
// }
</script>
