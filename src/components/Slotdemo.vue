<template>
<div class="slot-demo">
<div class="header">
<slot name="header"><h3>Default Header</h3></slot>
</div>
<div class="body">
<slot>Default content</slot>
</div>
<div class="footer">
<slot name="footer"><small>Default footer</small></slot>
</div>
</div>
</template>