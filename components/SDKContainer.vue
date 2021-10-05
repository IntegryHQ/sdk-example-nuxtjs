<template>
  <div id="my-sdk-container" />
</template>

<script lang="ts">
import { IntegryJS, Helpers } from '@integry/sdk'

export default {
  async mounted() {
    // Fill these in from the SDK deployments page
    const appKey = '<APP_KEY>'
    const deploymentId = '<DEPLOY_ID>'

    // This is intended for use in testing only!
    // Please refer to sdk.integry.io for more details
    const hash = await Helpers.getAuthHash('<USER_ID>', '<APP_SECRET>')

    const integryHandle = new IntegryJS({
      appKey,
      hash,
      userId,
      deploymentId,
    })

    integryHandle.init({
      containerId: 'my-sdk-container',
      renderMode: IntegryJS.RenderModes.INLINE,
    })
  },
}
</script>

<style>
#my-sdk-container {
  width: 100%;
  min-height: 480px;
}

#my-sdk-container .integry-container__tabbed-nav__tab--active {
  border-color: #00dc81;
}

#my-sdk-container .integry-container__flow-card {
  border-width: 2px;
}

#my-sdk-container .integry-container__flow-card:hover {
  border-color: #00dc81;
  border-width: 2px;
}

#my-sdk-container .integry-container__tabbed-nav__tab:hover {
  border-color: #00dc81;
}
</style>
