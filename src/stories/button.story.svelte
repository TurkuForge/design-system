<script lang="ts">
  import type { Hst as HstType } from '@histoire/plugin-svelte';
  import Button, { ButtonSize, ButtonStyle } from '../components/button.svelte';
  
  export let Hst: HstType; 

  let disabled = false;
  let content = 'Button text';
  let sizeSelect = ButtonSize.MEDIUM;
  let buttonStyle = ButtonStyle.PRIMARY;
</script>

<Hst.Story title="Button">
  <svelte:fragment slot="controls">
      <Hst.Text bind:value={content} title="Content" />
      <Hst.Checkbox bind:value={disabled} title="Disabled" />
      <Hst.Select 
        title="Size" 
        bind:value={sizeSelect} 
        options={[
          ButtonSize.XSMALL,
          ButtonSize.SMALL,
          ButtonSize.MEDIUM,
          ButtonSize.LARGE,
          ButtonSize.XLARGE
        ]} 
      />
      <Hst.Select 
        title="Style" 
        bind:value={buttonStyle} 
        options={[
          ButtonStyle.PRIMARY,
          ButtonStyle.SECONDARY
        ]} 
      />
  </svelte:fragment>
  <Hst.Variant title="default">
    <Button lable={content} style={buttonStyle} size={sizeSelect} disabled={disabled}/>
  </Hst.Variant>
  
</Hst.Story>
