<template>
  <div :id="id"></div>
</template>

<script>
const TcPlayer = window.TcPlayer

export default {
  props: {
    id: {
      type: String,
      default: 'tc-player'
    },
    width: {
      type: [Number, String],
      default: 640
    },
    height: {
      type: [Number, String],
      default: 480
    },
    listener: {
      type: Function,
      default () {
        return function (msg) {}
      }
    },
    live: {
      type: Boolean,
      default: true
    },
    options: {
      type: Object
    }
  },
  data () {
    return {
      tcPlayer: null
    }
  },
  mounted () {
    this.init()
  },
  methods: {
    init () {
      const options = {
        width: String(this.width),
        height: String(this.height),
        live: this.live,
        listener: this.listener,
        ...this.options
      }
      this.tcPlayer = new TcPlayer(this.id, options)
    },
    reset () {
      if (this.tcPlayer) {
        this.tcPlayer.destroy()
        this.init()
      }
    },
    play () {
      if (!this.tcPlayer) return
      return this.tcPlayer.play()
    },
    pause () {
      if (!this.tcPlayer) return
      return this.tcPlayer.pause()
    },
    togglePlay () {
      if (!this.tcPlayer) return
      return this.tcPlayer.togglePlay()
    },
    mute (muted) {
      if (!this.tcPlayer) return
      return this.tcPlayer.mute(muted)
    },
    volume (val) {
      if (!this.tcPlayer) return
      return this.tcPlayer.volume(val)
    },
    playing () {
      if (!this.tcPlayer) return
      return this.tcPlayer.playing()
    },
    duration () {
      if (!this.tcPlayer) return
      return this.tcPlayer.duration()
    },
    currentTime (time) {
      if (!this.tcPlayer) return
      return this.tcPlayer.currentTime(time)
    },
    fullscreen (enter) {
      if (!this.tcPlayer) return
      return this.tcPlayer.fullscreen(enter)
    },
    buffered () {
      if (!this.tcPlayer) return
      return this.tcPlayer.buffered()
    },
    switchClarity (clarity) {
      if (!this.tcPlayer) return
      return this.tcPlayer.switchClarity(clarity)
    }
  },
  destroyed () {
    if (this.tcPlayer) {
      this.tcPlayer.destroy()
    }
  }
}
</script>
