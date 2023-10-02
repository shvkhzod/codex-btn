<script lang="ts">
	import Button from "../components/button.svelte";
    
</script>
<div class="showcase">
    <Button 
    text="Button"
    type="solid" 
    size="small" 
    style="primary"
    iconType="none" 
    state="default" 
    leadingIcon="none" 
    trailingIcon ="none" />
 
</div>


<style>

    .showcase {
        padding: 60px;
        display: flex;
        flex-direction: column;
        gap: 16px;
    }

    h2 {
        color: white;

    }

 
    .row {

        width: 100%;
        display: flex;
        flex-direction: row;
        gap: 24px;
    
    }
</style>

