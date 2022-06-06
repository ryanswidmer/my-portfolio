<template>
    <nav role='navigation'>
      <div id="menuToggle">
        <!--
        A fake / hidden checkbox is used as click reciever,
        so you can use the :checked selector on it.
        -->
        <input type="checkbox" />
        
        <!--
        Some spans to act as a hamburger.
        
        They are acting like a real hamburger,
        not that McDonalds stuff.
        -->
        <span></span>
        <span></span>
        <span></span>        
        <!--
        Too bad the menu has to be inside of the button
        but hey, it's pure CSS magic.
        -->
        <ul id="menu">
          <li><a href="#">Home</a></li>
          <li><a href="#">About</a></li>
          <li><a href="#">Info</a></li>
          <li><a href="#">Contact</a></li>
          <li><a href="https://erikterwan.com/" target="_blank">Show me more</a></li>
        </ul>
      </div>
    </nav>
</template>

<style scoped>
a
{
  text-decoration: none;
  color: #1c1c1c;
  
  transition: color 0.3s ease;
}
a:hover
{
  color: #23c4c4;
  background-color: #1c1c1c;
}

#menuToggle
{
    z-index: 10;
    position: fixed;
    top: 50px;
    right: 50px;
    height: 100vh;

    -webkit-user-select: none;
    user-select: none;
}

#menuToggle input
{
  display: block;
  width: 40px;
  height: 32px;
  position: absolute;
  top: -7px;
  left: -5px;
  
  cursor: pointer;
  
  opacity: 0; /* hide this */
  z-index: 2; /* and place it over the hamburger */
  
  -webkit-touch-callout: none;
}

/*
 * Just a quick hamburger
 */
#menuToggle span
{
  display: block;
  width: 33px;
  height: 4px;
  margin-bottom: 5px;
  position: relative;
  
  background: #cdcdcd;
  border-radius: 3px;
  
  z-index: 1;
  
  transform-origin: 4px 0px;
  
  transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0),
              background 0.5s cubic-bezier(0.77,0.2,0.05,1.0),
              opacity 0.55s ease;
}

#menuToggle span:first-child
{
  transform-origin: 0% 0%;
}

#menuToggle span:nth-last-child(2)
{
  transform-origin: 0% 100%;
}

/* 
 * Transform all the slices of hamburger
 * into a crossmark.
 */
#menuToggle input:checked ~ span
{
  opacity: 1;
  transform: rotate(45deg) translate(-2px, -1px);
  background: #232323;
}

#menuToggle input:checked ~ span:nth-last-child(3)
{
  opacity: 0;
  transform: rotate(0deg) scale(0.2, 0.2);
}

#menuToggle input:checked ~ span:nth-last-child(2)
{
  opacity: 1;
  transform: rotate(-45deg) translate(0, -1px);
}

/*
 * Make this absolute positioned
 * at the top left of the screen
 */
#menu
{
  position: absolute;
  width: 25vw;
  height: 100vh;
  margin: -100px 0 0 0;
  padding: 50px;
  padding-top: 25vh;
  right: -100px;
  
  background: #ededed;
  list-style-type: none;
  -webkit-font-smoothing: antialiased;
  /* to stop flickering of text in safari */
  
  transform-origin: 0% 0%;
  transform: translate(100%, 0);
  
  transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0);
}

#menu li
{
  padding: 30px 0;
  text-align: left;
  font-size: clamp(30px, 2.8vw, 54px);
  margin: 0;
  font-weight: 700;
  justify-content: center;
}
/*
 * Fade in the left when checked
 */
#menuToggle input:checked ~ ul
{
  transform: none;
  opacity: 1;
}

@media screen and (max-width: 768px) {
  #menu {
    transform: none;
    opacity: 0;

    transition: opacity 0.5s cubic-bezier(0.77,0.2,0.05,1.0);
  }
}
</style>
