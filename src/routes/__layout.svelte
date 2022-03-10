<script>
  import 'carbon-components-svelte/css/g90.css'
  import {
    Header,
    HeaderUtilities,
    HeaderAction,
    HeaderGlobalAction,
    SideNav,
    SideNavItems,
    SideNavMenu,
    SideNavMenuItem,
    SideNavLink,
    SkipToContent,
  } from 'carbon-components-svelte'
  import SettingsAdjust20 from 'carbon-icons-svelte/lib/SettingsAdjust20'
  import UserAvatarFilledAlt20 from 'carbon-icons-svelte/lib/UserAvatarFilledAlt20'

  let isSideNavOpen = false
  let isOpen1 = false
</script>

<Header platformName="Junior Adventurers" bind:isSideNavOpen>
  <svelte:fragment slot="skip-to-content">
    <SkipToContent />
  </svelte:fragment>
  <HeaderUtilities>
    <HeaderGlobalAction aria-label="Settings" icon={SettingsAdjust20} />
    <HeaderAction
      bind:isOpen={isOpen1}
      icon={UserAvatarFilledAlt20}
      closeIcon={UserAvatarFilledAlt20}
    />
  </HeaderUtilities>
</Header>

<SideNav bind:isOpen={isSideNavOpen}>
  <SideNavItems>
    <SideNavLink text="Link 1" />
    <SideNavLink text="Link 2" />
    <SideNavLink text="Link 3" />
    <SideNavMenu text="Menu">
      <SideNavMenuItem href="/" text="Link 1" />
      <SideNavMenuItem href="/" text="Link 2" />
      <SideNavMenuItem href="/" text="Link 3" />
    </SideNavMenu>
  </SideNavItems>
</SideNav>

<main>
  <slot />
</main>

<style>
  main {
    margin: 5rem 2rem 2rem;
  }
</style>
