<template>
  <nav id="sidebar-right" class="sidebar sidebar__right">
    <div class="d-flex align-items-center justify-content-center my-3">
      <h4 class="text__white">
        Leaderboard
      </h4>
    </div>
    <b-container>
      <b-row>
        <b-col cols="12" style="min-height: calc(100vh - 191px)">
          <b-table
            class="table-data"
            :fields="fields"
            :items="[{ player: 'NoManSky' }, { player: 'NoManSky2' }]"
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
    </b-container>
    <footer class="footer-countdown">
      <b-container>
        <b-row class="footer-countdown-section">
          <b-col cols="12" class="d-flex justify-content-center">
            <div class="footer-countdown__timer">
              24
            </div>
            <div class="footer-countdown__separator">
              :
            </div>
            <div class="footer-countdown__timer">
              35
            </div>
            <div class="footer-countdown__separator">
              :
            </div>
            <div class="footer-countdown__timer">
              50
            </div>
          </b-col>
        </b-row>
      </b-container>
    </footer>
  </nav>
</template>

<script>
export default {
  data () {
    return {
      busy: false,
      fields: [
        { key: 'rank', label: 'No', thStyle: { width: '50px' } },
        { key: 'player', label: 'Pemain' }
      ]
    }
  }
}
</script>
