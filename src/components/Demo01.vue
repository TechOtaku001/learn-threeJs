<!-- demo01 -->
<template>
  <div class="demo01" ref="demo01"></div>
</template>

<script>
import * as Three from 'three'
export default {
  data () {
    return {
      scene: null,
      camera: null,
      renderer: null
    }
  },
  created() {
    this.init()
  },
  mounted() {
    this.setRenderer()
    this.setScene()
    this.setCamera()
    this.$refs.demo01.appendChild(this.renderer.domElement)
    this.renderer.render(this.scene, this.camera)
  },
  methods: {
    init() {
      this.scene = new Three.Scene()
      this.camera = new Three.PerspectiveCamera(45, window.innerWidth/window.innerHeight, 0.1, 1000)
      this.renderer = new Three.WebGLRenderer()
    },
    createPlane() {
      const planeGeometry = new Three.PlaneGeometry(60, 20, 1, 1)
      const planeMaterial = new Three.MeshBasicMaterial({color: 0xcccccc})
      const plane = new Three.Mesh(planeGeometry, planeMaterial)
      plane.rotation.x = -0.5 * Math.PI
      plane.position.x = 15
      plane.position.y = 0
      plane.position.z = 0
      return plane
    },
    createCube() {
        const cubeGeometry = new Three.BoxGeometry(4, 4, 4)
        const cubeMaterial = new Three.MeshBasicMaterial({
            color: 0xff0000,
            wireframe: true
        })
        const cube = new Three.Mesh(cubeGeometry, cubeMaterial)
        cube.position.x = -4
        cube.position.y = 3
        cube.position.z = 0
        return cube
    },
    createSphere() {
        const sphereGeometry = new Three.SphereGeometry(4, 20, 20)
        const sphereMaterial = new Three.MeshBasicMaterial({
          color: 0x7777ff,
          wireframe: true
        })
        const sphere = new Three.Mesh(sphereGeometry, sphereMaterial)
        sphere.position.x = 20
        sphere.position.y = 4
        sphere.position.z = 2
        return sphere
    },
    setRenderer() {
      if(this.renderer) {
        this.renderer.setClearColor(0xEEEEEE)
        this.renderer.setSize(window.innerWidth, window.innerHeight)
      }
    },
    setScene() {
      if (this.scene) {
        const axes = new Three.AxesHelper(20)
        this.scene.add(axes)
        const plane = this.createPlane()
        this.scene.add(plane)
        const cube = this.createCube()
        this.scene.add(cube)
        const sphere = this.createSphere()
        this.scene.add(sphere)
      }
    },
    setCamera() {
      if (this.camera) {
        this.camera.position.x = -30
        this.camera.position.y = 40
        this.camera.position.z = 30
        this.camera.lookAt(this.scene.position)
      }
    }
  }
}

</script>
<style>
.demo01 {
    width: 100%;
    height: 100%;
}
</style>