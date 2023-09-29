<script lang="ts">
	import Button from "../components/button.svelte";
    
</script>
<div class="showcase">
    <h2>Small</h2>
    <div class="row">
  
        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="primary"
        iconType="none" 
        state="default" 
        leadingIcon="none" 
        trailingIcon ="none" />

          
        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="primary"
        iconType="leading" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="none" />

        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="primary"
        iconType="trailing" 
        state="default" 
        leadingIcon="none" 
        trailingIcon ="menu" />

        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="primary"
        iconType="leadingTrailing" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="menu" />

        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="primary"
        iconType="standalone" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="none" />
    </div>

    <div class="row">
  
        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="secondary"
        iconType="none" 
        state="default" 
        leadingIcon="none" 
        trailingIcon ="none" />

          
        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="secondary"
        iconType="leading" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="none" />

        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="secondary"
        iconType="trailing" 
        state="default" 
        leadingIcon="none" 
        trailingIcon ="menu" />

        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="secondary"
        iconType="leadingTrailing" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="menu" />

        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="secondary"
        iconType="standalone" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="none" />
    </div>

    <div class="row">
  
        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="danger"
        iconType="none" 
        state="default" 
        leadingIcon="none" 
        trailingIcon ="none" />

          
        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="danger"
        iconType="leading" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="none" />

        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="danger"
        iconType="trailing" 
        state="default" 
        leadingIcon="none" 
        trailingIcon ="menu" />

        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="danger"
        iconType="leadingTrailing" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="menu" />

        <Button 
        text="Button"
        type="solid" 
        size="small" 
        style="danger"
        iconType="standalone" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="none" />
    </div>

    <h2>Medium</h2>
    <div class="row">
  
        <Button 
        text="Button"
        type="outline" 
        size="medium" 
        style="danger"
        iconType="leadingTrailing" 
        state="hover" 
        leadingIcon="plus" 
        trailingIcon ="plus" />

          
        <Button 
        text="Button"
        type="ghost" 
        size="medium" 
        style="secondary"
        iconType="leading" 
        state="hover" 
        leadingIcon="plus" 
        trailingIcon ="none" />

        <Button 
        text="Button"
        type="solid" 
        size="medium" 
        style="danger"
        iconType="trailing" 
        state="disabled" 
        leadingIcon="none" 
        trailingIcon ="menu" />

        <Button 
        text="Button"
        type="outline" 
        size="medium" 
        style="danger"
        iconType="leadingTrailing" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="menu" />

        <Button 
        text="Button"
        type="solid" 
        size="medium" 
        style="danger"
        iconType="standalone" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="none" />
    </div>

 
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

