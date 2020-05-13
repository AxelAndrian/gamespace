<template>
  <div>
    <Content title="DOTA 2 LEADERBOARDS">
      <template #content>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ratione molestias similique architecto laborum excepturi amet soluta aut ipsa doloribus reprehenderit asperiores sunt aspernatur doloremque totam facere, quae distinctio deleniti ullam!</p>
        <b-row>
          <b-col cols="12">
            <b-table
              class="table-data"
              :fields="fields"
              :items="[{ player: 'NoManSky', win: '1', lose: '3', draw: '0', lm: '12' }, { player: 'NoManSky2', win: '1', lose: '3', draw: '0', lm: '12' }]"
              :busy="busy"
              show-empty
              responsive
            >
              <template v-slot:table-busy>
                <div class="text-center">
                  <b-spinner variant="orange" class="align-middle mr-2" />
                  <strong>Harap Tunggu...</strong>
                </div>
              </template>

              <template v-slot:cell(rank)="data">
                {{ data.index + 1 }}
              </template>
            </b-table>
          </b-col>
        </b-row>
      </template>
    </Content>
  </div>
</template>

<script>
import Content from '@/components/Content.vue'

export default {
  components: {
    Content
  },
  data () {
    return {
      busy: false,
      fields: [
        { key: 'rank', label: 'No', thStyle: { width: '50px' } },
        { key: 'player', label: 'Pemain' },
        { key: 'win', label: 'W', thStyle: { width: '50px' } },
        { key: 'lose', label: 'L', thStyle: { width: '50px' } },
        { key: 'draw', label: 'D', thStyle: { width: '50px' } },
        { key: 'lm', label: 'LM', thStyle: { width: '50px' } }
      ]
    }
  }
}
</script>
