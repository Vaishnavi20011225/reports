<template>
    <div class="body">
        <PowerBIReportEmbed :cssClassName="pbi" :embedConfig=config>
        </PowerBIReportEmbed>
    </div>
</template>

<script>
import { PowerBIReportEmbed } from 'powerbi-client-vue-js';
import * as powerbi from 'powerbi-client';

export default
    {
        components: { PowerBIReportEmbed },
        data() {
            const config = {
                type: "",//report/dashboard
                id: '',//reportid/dashboardid
                embedUrl: "",//embed url 
                //generate access token
                accessToken: "",
                tokenType: powerbi.models.TokenType.Embed,
                settings: {
                    panes: {
                        filters: {
                            expanded: false,
                            visible: false
                        }
                    },
                    background: powerbi.models.BackgroundType.Transparent,
                }
            }
            return { config }
        }
    }
</script>

<style>
#reportContainer {
    height: 100vh;
}
</style>