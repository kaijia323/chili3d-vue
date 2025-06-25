<script setup>
// prettier-ignore
new window.Chili3d.AppBuilder()
    .useIndexedDB()
    .useWasmOcc()
    .useThree()
    .useUI()
    .build()
    .then(x => {
        // document.body.removeChild(loading)
        console.log('chili3d 加载完成')
    })
    .catch((err) => {
        console.error(err);
    });
</script>

<template>
  <div id="app"></div>
</template>
