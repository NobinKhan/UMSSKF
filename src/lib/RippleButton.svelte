
<h1>Ripple-without-JS</h1>
<p>Material Design ripple effect in without a single line of JS.</p>
<button class="btn ripple">Click here</button>

<style>

/*Create ripple effec*/
.ripple {
  position: relative;
  overflow: hidden;
  transform: translate3d(0, 0, 0);
}

.ripple:after {
  content: "";
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  pointer-events: none;
  background-image: radial-gradient(circle, #fff 10%, transparent 10.01%);
  background-repeat: no-repeat;
  background-position: 50%;
  transform: scale(10, 10);
  opacity: 0;
  transition: transform 0.5s, opacity 1s;
}

.ripple:active:after {
  transform: scale(0, 0);
  opacity: 0.3;
  transition: 0s;
}

/* btn styles */
.btn {
  background-color: #1D27E7;
  color: #fff;
  min-width: 160px;
  font-size: 1.3rem;
  padding: 10px 20px;
  box-sizing: border-box;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  text-decoration: none;
  transition: 0.3s;
  border-radius: 4px;
  border: 2px solid #1D27E7;
  outline: none;
  white-space: nowrap;
  font-weight: 500;
  vertical-align: middle;
  margin: 5px;
  box-shadow: 0 0 2px -2px rgba(29, 39, 231, 0.1), 0 0 3px 0 rgba(29, 39, 231, 0.1), 0 0 5px 0 rgba(29, 39, 231, 0.1), 0 2px 2px -4px rgba(29, 39, 231, 0.1), 0 4px 8px 0 rgba(29, 39, 231, 0.1), 0 2px 15px 0 rgba(29, 39, 231, 0.1);
}

.btn:hover {
  background-color: #131BB4;
  border-color: #131BB4;
  color: #fff;
}
</style>