<template>
    <div class="row justify-content-center">
        <div class="col-8">
            <div v-if="camara">
                <h2 class="jh-entity-heading"><span v-text="$t('gatewayApp.eventosCamara.detail.title')">Camara</span> {{camara.id}}</h2>
                <dl class="row jh-entity-details">
                    <dt>
                        <span v-text="$t('gatewayApp.eventosCamara.descricao')">Descricao</span>
                    </dt>
                    <dd>
                        <span>{{camara.descricao}}</span>
                    </dd>
                    <dt>
                        <span v-text="$t('gatewayApp.eventosCamara.estado')">Estado</span>
                    </dt>
                    <dd>
                        <!--<span>{{camara.estado}}</span>-->
                        <span v-if="camara.estado==true">Ativa</span>
                        <span v-if="camara.estado==false">Inativa</span>
                    </dd>
                    <dt>
                        <span v-text="$t('gatewayApp.eventosCamara.enderecoIp')">Endereco Ip</span>
                    </dt>
                    <dd>
                        <span>{{camara.enderecoIp}}</span>
                    </dd>
                    <dt>
                        <span v-text="$t('gatewayApp.eventosCamara.enderecoMac')">Endereco Mac</span>
                    </dt>
                    <dd>
                        <span>{{camara.enderecoMac}}</span>
                    </dd>
                </dl>
                <button type="submit"
                        v-on:click.prevent="previousState()"
                        class="btn btn-info">
                    <font-awesome-icon icon="arrow-left"></font-awesome-icon>&nbsp;<span v-text="$t('entity.action.back')"> Back</span>
                </button>
                <router-link v-if="camara.id" :to="{name: 'CamaraEdit', params: {camaraId: camara.id}}" tag="button" class="btn btn-primary">
                    <font-awesome-icon icon="pencil-alt"></font-awesome-icon>&nbsp;<span v-text="$t('entity.action.edit')"> Edit</span>
                </router-link>
            </div>
        </div>
    </div>
</template>

<script lang="ts" src="./camara-details.component.ts">
</script>
