<script lang="typescript">
  let selectedTab = 0
  let count = 0
  let textFieldValue = 'new'
</script>

<page>
  <actionBar title="Svelte Native Prac" />
  <bottomNavigation bind:selectedIndex={selectedTab} tabsPosition="bottom">
    <!-- The bottom tab UI is created via TabStrip (the containier) and TabStripItem (for each tab)-->
    <tabStrip>
      <tabStripItem>
        <label text="Home" />
        <image src="font://" class="fas t-24" />
      </tabStripItem>
      <tabStripItem class="special">
        <label text="Account" />
        <image src="font://" class="fas t-24" />
      </tabStripItem>
      <tabStripItem class="special">
        <label text="Search" />
        <image src="font://" class="fas t-24" />
      </tabStripItem>
    </tabStrip>

    <!-- The number of TabContentItem components should corespond to the number of TabStripItem components -->
    <tabContentItem>
      <stackLayout>
        <wrapLayout class="counter">
          <label text={count} class="h2 text-center" />
          <textField bind:text={textFieldValue} />
          <button text="+1" class="btn inc" on:tap={() => count++} />
          <button text="-1" class="btn dec" on:tap={() => count > 0 && count--} />
        </wrapLayout>
      </stackLayout>
    </tabContentItem>
    <tabContentItem>
      <gridLayout><label text="Account Page" class="h2 text-center" /></gridLayout>
    </tabContentItem>
    <tabContentItem>
      <gridLayout><label text="Search Page" class="h2 text-center" /></gridLayout>
    </tabContentItem>
  </bottomNavigation>
</page>

<style>
  .counter {
    border-width: 1px;
    border-color: #111111;
    margin-top: 10px;
    margin-bottom: 10px;
    border-radius: 5px;
  }
  .btn {
    border-radius: 5px;
    color: #fff;
    width: 64px;
  }
  .inc {
    background-color: #269f42;
  }

  .dec {
    background-color: #cc3300;
  }
</style>
