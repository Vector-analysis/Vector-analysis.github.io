---
title: "Zhaofeng Peng - Gallery"
layout: piclay
excerpt: "Zhaofeng Peng -- Gallery"
sitemap: false
permalink: /gallery/
---

# Gallery

<!--**Under Construction...**-->


<h2>Lissajous Figure Unity Project</h2>

I am very interested in video game development, so I decided to try Unity (a game engine). Instead of starting with a complicated game project, I began with a Lissajous figure simulator. Here are some snapshots.

<figure class="fourth">
  <img src="{{ site.url }}{{ site.baseurl }}/images/Lissajous/Fig1.png" style="width: 200px">
  <img src="{{ site.url }}{{ site.baseurl }}/images/Lissajous/Fig2.png" style="width: 200px">
  <img src="{{ site.url }}{{ site.baseurl }}/images/Lissajous/Fig3.png" style="width: 200px">
  <img src="{{ site.url }}{{ site.baseurl }}/images/Lissajous/Fig4.png" style="width: 200px">
</figure>


<h2>Music</h2>

Here is a piece of music I created called ‘弈’ (which means 'Chess-playing').

<audio controls controlsList="nodownload">
  <source src="{{ site.url }}{{ site.baseurl }}/downloads/弈.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>


Here is another piece called ‘我们的征途’ (which means 'Our Grand Expedition').

<audio controls controlsList="nodownload">
  <source src="{{ site.url }}{{ site.baseurl }}/downloads/我们的征途.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>


<!--Prevent multiple audio elements from playing simultaneously-->
<script>
  const audios = document.querySelectorAll('audio');

  audios.forEach(audio => {
    audio.addEventListener('play', () => {
      audios.forEach(otherAudio => {
        if (otherAudio !== audio) {
          otherAudio.pause();
        }
      });
    });
  });
</script>


<h2>Gallery of Fluids</h2>

<!--I really enjoy the beauty of some flow patterns. Here is a peek. Images are sourced from the Internet.-->
I find the beauty of certain flow patterns truly captivating. Take a look at these examples sourced from the Internet.

<div markdown="0" id="carousel" class="carousel slide" data-ride="carousel" data-interval="4000" data-pause="hover" >
    <!-- Menu -->
    <ol class="carousel-indicators">
        <li data-target="#carousel" data-slide-to="0" class="active"></li>
        <li data-target="#carousel" data-slide-to="1"></li>
        <li data-target="#carousel" data-slide-to="2"></li>
        <!--<li data-target="#carousel" data-slide-to="3"></li>
        <li data-target="#carousel" data-slide-to="4"></li>
        <li data-target="#carousel" data-slide-to="5"></li>
        <li data-target="#carousel" data-slide-to="6"></li>-->
    </ol>

    <!-- Items -->
    <div class="carousel-inner" markdown="0">
        <div class="item active">
            <!--<img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/QPI_Rh.jpg" alt="Slide 1" />-->
            <img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/Kármán_vortex_street.jpg" alt="Slide 1" />
        </div>
        <div class="item">
            <!--<img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/SmartTipSide.jpg" alt="Slide 2" />-->
            <img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/Kelvin_Helmholtz_wave_clouds.jpg" alt="Slide 2" />
        </div>
        <div class="item">
            <!--<img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/SaphireSTM2.jpg" alt="Slide 3" />-->
            <img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/Water_Drop.jpg" alt="Slide 3" />
        </div>
        <div class="item">
            <!--<img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/lab.jpg" alt="Slide 4" />-->
            <img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/Saffman_Taylor.jpg" alt="Slide 4" />
        </div>
        <div class="item">
            <!--<img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/Fig_Science_Web.jpg" alt="Slide 5" />-->
            <img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/Duck_wave.jpg" alt="Slide 5" />
        </div>       
        <!--<div class="item">
            <img src="{{ site.url }}{{ site.baseurl }}/images/slider7001400/BSCCO2gap2.jpg" alt="Slide 6" />
        </div>-->
    </div>
  <a class="left carousel-control" href="#carousel" role="button" data-slide="prev">
    <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="right carousel-control" href="#carousel" role="button" data-slide="next">
    <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>


<!--Jump to: [Leiden](#leiden), [ETHZ](#ethz), [Cornell](#cornell), [St Andrews](#st-andrews)


## Leiden

#### Timelapse of our STM assembling [(see LION news item)](https://www.physics.leidenuniv.nl/index.php?id=11573&news=867&type=lion&ln=EN):
<iframe width="560" height="315" src="https://www.youtube.com/embed/3iKvUMv1h5A" frameborder="0" allowfullscreen></iframe>

#### Gallery
(Right-click *'view image'* to see a larger image.)
{% assign number_printed = 0 %}
{% for pic in site.data.pictures_Leiden %}

{% assign even_odd = number_printed | modulo: 4 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-3 clearfix">
<img src="{{ site.url }}{{ site.baseurl }}/images/picpic/Gallery/{{ pic.image }}" class="img-responsive" width="95%" style="float: left" />
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd > 2 %}
</div>
{% endif %}


{% endfor %}

{% assign even_odd = number_printed | modulo: 4 %}
{% if even_odd == 1 %}
</div>
{% endif %}

{% if even_odd == 2 %}
</div>
{% endif %}

{% if even_odd == 3 %}
</div>
{% endif %}

<p> &nbsp; </p>

First advertisement.
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/picpic/WebpageLeiden_red.jpg" width="60%" >
</figure>


## ETHZ
From the [group of Andreas Wallraff](http://www.qudev.ethz.ch/).
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/picpic/WebpageETH_red.jpg" width="60%">
</figure>

## Cornell
From the [group of Seamus JC Davis](http://davisgroup.lassp.cornell.edu).
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/picpic/WebpageCornell_red.jpg" width="60%">
</figure>

## St Andrews
From the [group of Felix Baumberger](http://dqmp.unige.ch/baumberger/) (now at University of Geneva).
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/picpic/WebpageSTA_red.jpg" width="60%">
</figure>-->

