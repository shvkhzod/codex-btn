<script lang="ts">
	import Button from "../components/button.svelte";
    
</script>
<div class="showcase">
    <Button 
    text="Button"
    type="solid" 
    size="large" 
    style="primary"
    iconType="trailing" 
    state="default" 
    leadingIcon="plus" 
    trailingIcon ="menu" />


 
</div>


<style>

    .showcase {
        width: auto;
        padding: 60px;
        display: flex;
        flex-direction: column;
        gap: 16px;
    }

  

 
 
</style>

