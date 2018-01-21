<script>
import {Bar} from 'vue-chartjs'

export default {
  name: 'line1',
  mixins: [Bar],
  props: {
    lineData: {
      type: Array,
      default: () => {
        return []
      }
    }
  },
  data () {
    return {
      linedata1: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
        datasets: [
          {
            label: 'Datalabel',
            backgroundColor: '#f87979',
            data: []
          }
        ]
      },
      lineopts: {}
    }
  },
  methods: {
    flush () {
    }
  },
  watch: {
    lineData: {
      handler (val, oldVal) {
        this.linedata1.datasets[0].data = val
        this.flush()
      }
    }
  }
}
</script>
