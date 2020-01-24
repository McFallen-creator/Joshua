<body>
<html>

<div class="container">
  <section>
    <div class="image" data-type="background" data-speed="2"></div>
	  
	<div class="stuff" data-type="content"><h1>The Enviromental Impact of Acid Rain</h1><h3>Effects of Acid Rain of fish and wildlife</h3></div>
  </section>
		
<section>
    <div class="image" data-type="background" data-speed="7"></div>
    <div class="stuff" data-type="content"><h2>Acid Rain</h2><p>....</p></div>
  </section>

  <section>
    <div class="image" data-type="background" data-speed="6"></div>
    <div class="stuff" data-type="content">........</div>
  </section>

  <section>
    <div class="image" data-type="background" data-speed="5"></div>
    <div class="stuff" data-type="content">.........</div>
  </section>

  <section>
    <div class="image" data-type="background" data-speed="3"></div>
    <div class="stuff" data-type="content">........</div>
  </section>

  <section>
    <div class="image" data-type="background" data-speed="3"></div>
    <div class="stuff" data-type="content">Any questions or concerns please click the name in the bottom right hand corner, Thank You.</div>
  </section>
</div>

<div class="at-gmail"><a href="mailto:ramirez.joshua217@gmail.com" target="_blank">Joshua Ramirez</a></div>

</body>
</html>
<style>
  
@import "compass/css3";

@import url(https://fonts.googleapis.com/css?family=Open+Sans:400,300,700,600);

html, body {
  background-color: #2c3e50;
  font-family: 'Open Sans', sans-serif; 
}

.container {
  display: flex;
  align-content: center;
  align-items: center;
  flex-direction: column; 
  flex-wrap: nowrap;
  height: 100%;
  justify-content: space-around;
  position: relative;
  width: 100%; 

  section {
    width: 100%;
    height: 100vh;
    flex: 1;
    display: flex;
    text-align: center;
    position: relative;
    overflow: hidden;
    background-color: #000;

    &:nth-child(1) {
      .image {
        background-image: url(https://i.postimg.cc/tgMhTBgF/download.jpgiq=100&fm=jpg&w=1000);
      }
    }

    &:nth-child(2) {
      .image {
        background-image: url(https://i.postimg.cc/tC06Z1Nn/acd.jpgiq=100&fm=jpg&w=1000);
      }
    }

    &:nth-child(3) {
      .image {
        background-image: url(https://i.postimg.cc/prs37NZg/forest.jpg);
      }
    }

    &:nth-child(4) {
      .image {
        background-image: url(https://i.postimg.cc/MG4L1bT8/rain.jpgiq=100&fm=jpg&w=1000);
      }
    }

    &:nth-child(5) {
      .image {
        background-image: url(https://i.postimg.cc/C1qtFPgQ/water.jpgiq=100&fm=jpg&w=1000);
      }
    }

    &:nth-child(6) {
      .image {
        background-image: url(https://i.postimg.cc/L6nPhr75/weather.jpgiq=100&fm=jpg&w=1000);
      }
    }

    .image {
      background-attachment: fixed; 
      background-size: cover;
      //background-repeat: no-repeat;
      width: 100%;
      height: 100%;
      position: absolute;
      z-index: 500;
      opacity: 0.4;
    }

    .stuff {
      display: flex;
      flex-direction: column;
      flex-wrap: nowrap;
      height: 100%;
      width: 100%;
      max-width: 70%;
      justify-content: center;
      text-align: center;
      z-index: 1000;
      color: #e67e22;
      margin: 0 auto;
      font-size: 26px;
      position: relative;

      h2 {
        margin: 0px;
      }
      &:before, &:after {
        width: 100%;
        height: 1px;
        display: block;
        background-color: #d35400;
        content: "";
        margin: 30px 0;
      }
    }
  }
}

.at-gmail {
  position: fixed;
  right: 20px;
  bottom: 20px;
  color: #f1c40f;
  z-index: 5000;
  &:visited {
    color: #f1c40f;
  }
}

a {
  color: inherit;
  &:hover,
  &:focus {
    color: inherit;
    text-decoration: underline;
  }
  text-decoration: none;
}

</style>
<script>

// makes the parallax elements
function parallaxIt() {
  // create variables
  var $fwindow = $(window);
  var scrollTop = window.pageYOffset || document.documentElement.scrollTop;

  var $contents = [];
  var $backgrounds = [];

  // for each of content parallax element
  $('[data-type="content"]').each(function(index, e) {
    var $contentObj = $(this);

    $contentObj.__speed = ($contentObj.data('speed') || 1);
    $contentObj.__fgOffset = $contentObj.offset().top;
    $contents.push($contentObj);
  });

  // for each of background parallax element
  $('[data-type="background"]').each(function() {
    var $backgroundObj = $(this);

    $backgroundObj.__speed = ($backgroundObj.data('speed') || 1);
    $backgroundObj.__fgOffset = $backgroundObj.offset().top;
    $backgrounds.push($backgroundObj);
  });

  // update positions
  $fwindow.on('scroll resize', function() {
    scrollTop = window.pageYOffset || document.documentElement.scrollTop;

    $contents.forEach(function($contentObj) {
      var yPos = $contentObj.__fgOffset - scrollTop / $contentObj.__speed;

      $contentObj.css('top', yPos);
    })

    $backgrounds.forEach(function($backgroundObj) {
      var yPos = -((scrollTop - $backgroundObj.__fgOffset) / $backgroundObj.__speed);

      $backgroundObj.css({
        backgroundPosition: '50% ' + yPos + 'px'
      });
    });
  });

  // triggers winodw scroll for refresh
  $fwindow.trigger('scroll');
};

parallaxIt();

</script>
