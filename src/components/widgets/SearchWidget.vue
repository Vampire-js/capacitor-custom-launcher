<template>
<div class="rounded flex items-center p-3 mt-10" style="background:var(--tertiary);">
    <ion-icon name="search" class="text-2xl" style="color:var(--secondary);"/>
<input placeholder="Search anything" class="bg-transparent font-bold outline-none w-full mx-3 thing" style="color:var(--secondary)">
</div>
</template>


<style>
.thing::placeholder {
  color: var(--secondary);
  opacity: 1; /* Firefox */
}
</style>