<div id="loader" class="bg-black min-h-screen">
  <div class="loader">Into the NAHVERSE</div>
</div>

<style>
.loader {
  width: 400px;
  height: 50px;
  line-height: 50px;
  text-align: center;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  font-family: helvetica, arial, sans-serif;
  text-transform: uppercase;
  font-weight: 900;
  color: #fff;
  letter-spacing: 0.2em;
}

.loader::before,
.loader::after {
  content: "";
  display: block;
  width: 15px;
  height: 15px;
  background: #fff;
  position: absolute;
  animation: load 1.2s infinite alternate ease-in-out;
}

.loader::before {
  top: 0;
}

.loader::after {
  bottom: 0;
}

@keyframes load {
  0% {
    left: 0;
    height: 30px;
    width: 30px;
  }
  50% {
    height: 8px;
    width: 40px;
  }
  100% {
    left: 370px;
    height: 30px;
    width: 30px;
  }
}
</style>