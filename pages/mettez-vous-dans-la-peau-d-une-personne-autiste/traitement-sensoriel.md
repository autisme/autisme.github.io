---
layout: page
title:  "Traitement sensoriel"
permalink: /mettez-vous-dans-la-peau-d-une-personne-autiste/traitement-sensoriel
hide_header_link: true
oembed_image: /assets/posts/2017-08-13/opengraph.png
---


Beaucoup de personnes autistes ont des hyper ou hypo sensibilités. Que ce soit au niveau de la vue, de l'odorat, du toucher, ou encore de l'équilibre.
Pour donner quelques exemples, imaginez que vous pouvez voir le clignotement des néons et qu'entendre leur grésillement continu fini par ne plus être supportable,
que vous ne supportez les lumières trop vives ou les lampes qui clignotent. Vous avez du mal à fixer les objets ou le texte que vous lisez
et cela vous donne mal à la tête.
Au contraire, certaines personnes avec autisme peuvent rechercher une forte stimulation visuelle.

Imaginez ce que cela serait pour vous si vous deviez passer vos journées à travailler dans un tel environnement&nbsp;:
<!-- neon -->
<canvas id="fig_neon" width="700" height="451" style="border: 1px solid black; margin: 0 auto 20px auto; display: block;"></canvas>


Les personnes avec autisme peuvent être également hypersensibles aux bruits. Imaginez que vous seul entendez le bruit du crissement de la craie sur le tableau.
Ce bruit est très énervant mais les autres personnes ne comprennent pas pourquoi vous vous énervez.
De même, certaines personnes ont du mal à différencier la parole des bruits et doivent attentivement et conscieusement écouter tout ce qu'il se passe autour d'elles pour identifier de potentielles voix.
Elles peuvent donner l'impression de ne pas vous écouter lorsque vous leurs parlez alors qu'il leur faut juste plus de temps pour analyser ce que vous dites.

Le toucher et le goût et l'odorat ne sont pas épargnés.
Certaines personnes ne supportent pas l'odeur de certains lieux, le goût ou la texture de certains aliments, etc.
Cela peut entraîner des difficultés pour varier les repas et mener à toujours manger les mêmes aliments.
Certaines personnes peuvent également rechercher certaines odeurs, goût ou textures qu'elles apprécient.
Par exemple, 


Généralement les environnements comportent plusieurs types de stimulations simultanément, ce qui rend l'ensemble difficile à supporter.
Regardez la vidéo ci-dessous, qui vous montre ce qu'il faut endurer en allant dans une galerie marchande&nbsp;:

<iframe width="560" height="315" src="https://www.youtube.com/embed/DgDR_gYk_a8" frameborder="0" style="border: 1px solid black; margin: 0 auto 0 auto; display: block;" allowfullscreen></iframe>

Cela peut être encore plus compliqué dans les moments où la personne est fatiguée, comme les fins de journées par exemple.
Cela peut mener à ce qui est appelé un «&nbsp;effondrement autistique&nbsp;» (ou *meltdown* en anglais).
Vous n'êtes alors plus capable de faire face à l'environnement. Vous êtes totalement submergés et vous n'êtes plus capable de traiter les informations de votre environnement
 ni de vous contrôler. La seule chose à faire pour vous calmer est de vous reposer.
Vu de l'extérieur, cela ressemble à une grosse colère et beaucoup de personnes ne font pas la différence.

Toutefois, ce traitement sensoriel différent peut parfois présenter un avantage.
Par exemple, beaucoup de personnes avec autisme remarquent des détails que la plupart des gens ne voient pas.
Combien de temps, mettrez-vous pour trouver Charlie dans l'image ci-dessous&nbsp;?

<!-- ou est charlie ? -->
<canvas id="game_waldo" width="700" height="500" style="border: 1px solid black; margin: 0 auto 0 auto; display: block;"></canvas>

<p>&nbsp;</p>

<div class="highlight">
<ol>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/qu-est-ce-que-l-autisme">Introduction - Qu'est-ce que l'autisme&nbsp;?</a></li>
 <li>Traitement sensoriel</li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/communication">Communication</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/langage-non-verbal">Langage non verbal</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/socialisation">Socialisation</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/imprevus-anxiete-concentration">Imprévus, anxiété et concentration</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/capacites-et-potentiels">Capacités et potentiels</a></li>
</ol>
</div>


---

<small>Images issues de <a href="https://whereswaldoemotionally.files.wordpress.com/" rel="nofollow">https://whereswaldoemotionally.files.wordpress.com</a>, <a href="https://www.glassdoor.com" rel="nofollow">https://www.glassdoor.com</a>.</small>

<script type="text/javascript">
  function neon() {
    var canvas = document.getElementById('fig_neon');
    var ctx = canvas.getContext('2d');
    var refresh = 100;
    var status = {'status': 'pause', 'interval': undefined};
    var images = {
      'on': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/neon/on.jpg'; return i;}(),
      'off': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/neon/off.jpg'; return i;}()
    }
    var lightning = 5000;
    var flicker = 5;
    this.play = function() {
      if ( 'play' == status['status'])
        return;
      status['interval'] = setInterval(function() {
        draw();
      }, refresh);
      
      status['status'] = 'play';
    }
    this.pause = function() {
      if ( 'pause' == status['status'])
        return;
      clearInterval(status['interval']);
      status['status'] = 'pause';
    }
    this.canvas = function() {
      return canvas;
    }
    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
//      console.log(lightning);
      lightning -= refresh;
      if (lightning < 0) {
        ctx.drawImage(images['off'], 0, 0);
        flicker -= 1;
        if (flicker < 0) {
          /* pause */
          flicker = Math.random() * (4 - 2) + 2;
          lightning = Math.random() * (5000 - 2000) + 2000;
        } else {
          lightning = Math.random() * (2*refresh - (refresh)) + (refresh);
        }
      } else {
        ctx.drawImage(images['on'], 0, 0);
      }
    }
  }

  function waldo() {
    var self = this;
    waldos = [
     {'src': '/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/waldo/background1.jpg', 'waldo': {'x': 514.5, 'y': 170}},
     {'src': '/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/waldo/background2.jpg', 'waldo': {'x': 512.5, 'y': 116}},
     {'src': '/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/waldo/background3.jpg', 'waldo': {'x': 348.5, 'y': 103}},
     {'src': '/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/waldo/background4.jpg', 'waldo': {'x': 484.5, 'y': 181}},
     {'src': '/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/waldo/background5.jpg', 'waldo': {'x': 300.5, 'y': 138}}
    ]
    var waldo = waldos[Math.floor((Math.random() * waldos.length))];
    var canvas = document.getElementById('game_waldo');
    var ctx = canvas.getContext('2d');
    var background = new Image();
    background.src = waldo['src'];
    var tmp = new Image();
    var zoom = 6;
    var targetbox = 10;
    var start = false;
    var win = false;
    var chronos;
    var chronos_fixed;
    var refresh = 10;
    var mouse = {'x': undefined, 'y': undefined};

    var status = {'status': 'pause', 'interval': undefined};

    this.play = function() {
      if ( 'play' == status['status'])
        return;
      canvas.onmousemove = move;
      canvas.onclick = click;
      status['interval'] = setInterval(function() {
        chronos += refresh;
        draw();
      }, refresh);
      status['status'] = 'play';
    }
    this.pause = function() {
      if ( 'pause' == status['status'])
        return;
      canvas.onmousemove = function(e) {}
      canvas.onclick = function(e) {}
      clearInterval(status['interval']);
      status['status'] = 'pause';
    }
    this.canvas = function() {
      return canvas;
    }


    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.drawImage(background, 0, 0, 700, 500);
      if (true == win) {
        ctx.fillStyle = "rgba(255, 255, 255, 0.7)";
        ctx.beginPath();
        ctx.rect(0, 0, 700, 500);
        ctx.fill();

        ctx.beginPath();
        ctx.fillStyle = "#111";
        ctx.rect((700/2)-100, (500/2)-40, 200, 60);
        ctx.stroke();
        ctx.textAlign = "center";
        ctx.font = "25px Arial";
        ctx.fillText("Recommencer",700/2,500/2);
        ctx.font = "20px Arial";
        ctx.fillText("Bravo",700/2,(500/2)-100);
        ctx.fillText("(" + (chronos_fixed/1000).toFixed(2) + " secondes)",700/2,(500/2)-75);
        return;
      }

      if (false == start) {
        ctx.beginPath();
        ctx.fillStyle = "rgba(255, 255, 255, 0.7)";
        ctx.rect(0, 0, 700, 500);
        ctx.fill();

        ctx.beginPath();
        ctx.fillStyle = "#111";
        ctx.rect((700/2)-100, (500/2)-40, 200, 60);
        ctx.stroke();
        ctx.textAlign = "center";
        ctx.font = "30px Arial";
        ctx.fillText("Commencer",700/2,500/2);
        return;
      }

      if (undefined == mouse['x'] || undefined == mouse['y']) {
        return;
      }
      ctx.drawImage(background, (mouse['x']*background.width/700) - ((700/zoom)/2), (mouse['y']*background.height/500) - ((500/zoom)/2), 700/zoom, 500/zoom, mouse['x'] - 75, mouse['y'] - 75, 150, 150);

      ctx.fillStyle = "#111";
      ctx.textAlign = "center";
      ctx.font = "30px Arial";
      ctx.fillText(""+(chronos/1000).toFixed(2),50, 40);


    }
    function move(e) {
      var r = canvas.getBoundingClientRect();
      mouse['x']=parseInt(e.clientX) - r.left;
      mouse['y']=parseInt(e.clientY) - r.top;

      if (false == start || true == win) {
        if ((mouse['x'] > (700/2)-100) && (mouse['y'] > (500/2)-40) && (mouse['x'] < (700/2)+100) && (mouse['y'] < (500/2)+20)) {
          canvas.style.cursor = 'pointer';
        } else {
          canvas.style.cursor = 'default';
        }
        return;
      }
      canvas.style.cursor = 'pointer';
      draw();
    }

    function click(e) {
      var r = canvas.getBoundingClientRect();
      var x = parseInt(e.clientX) - r.left;
      var y = parseInt(e.clientY) - r.top;
      if (false == start || true == win) {
        if ((mouse['x'] > (700/2)-100) && (mouse['y'] > (500/2)-40) && (mouse['x'] < (700/2)+100) && (mouse['y'] < (500/2)+20)) {
          if ( true == win ) {
            waldo = waldos[Math.floor((Math.random() * waldos.length))];
            background.src = waldo['src'];
          } else {
          }
          start = true;
          win = false;
          chronos = 0.0;
          draw();
        }
        return;
      }
      if ((x > waldo['waldo']['x']-targetbox) && (x < waldo['waldo']['x']+targetbox) && (y > waldo['waldo']['y']-targetbox) && (y < waldo['waldo']['y']+targetbox)) {
         win = true;
         chronos_fixed = chronos;
         draw();

      }
      console.log('x:' + x + ' y:' + y);
    }
  }

  function isScrolledIntoView(el) {
    var elemTop = el.getBoundingClientRect().top;
    var elemBottom = el.getBoundingClientRect().bottom;

    var isVisible = ((elemTop >= 0) && (elemTop <= window.innerHeight)) || ((elemBottom >= 0) && (elemBottom <= window.innerHeight)) || ((elemTop < 0) && (elemBottom > window.innerHeight));
    return isVisible;
  }



  document.body.onload = function() {
    var canvas = [new neon(), new waldo()];
    function load_visible() {
      for (var i = 0; i < canvas.length ; i++) {
        if (isScrolledIntoView(canvas[i].canvas())) {
          canvas[i].play();
        } else {
          canvas[i].pause();
        }
      }
    }
    document.body.onscroll = load_visible;
    document.body.onresize = load_visible;
    load_visible();
  }

</script>
