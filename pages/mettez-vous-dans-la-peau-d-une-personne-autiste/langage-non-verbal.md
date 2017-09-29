---
layout: page
title:  "Langage non verbal"
permalink: /mettez-vous-dans-la-peau-d-une-personne-autiste/langage-non-verbal
hide_header_link: true
oembed_image: /assets/posts/2017-08-13/opengraph.png
---

Le langage non verbal est souvent difficile à comprendre et à utiliser.
Imaginez ce que cela serait pour vous que de vivre dans un monde dans lequel vous ne devez compter uniquement sur ce que l'on vous dit pour comprendre le sens d'une phrase.

Imaginez que vous n'arrivez pas à regarder votre interlocuteur dans les yeux car identifier l'expression du regard vous est difficile et que cela vous distrait de vos pensées.
Certaines personnes avec autisme n'arrivent pas à regarder les personnes dans les yeux pour cette raison, d'autres regardent intensément les yeux sans détourner régulièrement leur regard. 
Cela peut générer des problèmes de communications à la fois pour la personne autiste et son interlocuteur.
Les personnes non autistes peuvent penser que si l'on ne les regarde pas dans les yeux, c'est que la personne est suspecte ou a quelque chose à cacher.
Au contraire trop regarder dans les yeux met la personne mal à l'aise.
Du point de vue de la personne avec autisme,
 vous pouvez par exemple vous demander pour quelle raison vous êtes félicité après avoir fait une bêtise puisque l'on vous aura dit&nbsp;: «&nbsp;Tu es fier de toi j'espère !&nbsp;» avec
un air en colère mais vous n'aurez considéré uniquement le texte et non l'expression du visage affichée.

Comprendre les expressions faciales est difficile pour beaucoup de personnes avec autisme.
Êtes-vous capable de déterminer les expressions des yeux suivants&nbsp;?
<!-- test des visages -->
<canvas id="game_eyes" width="700" height="1050" style="border: 1px solid black; margin: 0 auto 0 auto; display: block;"></canvas>


Cet exercice est souvent difficile. Dans la vrai vie, cela est d'autant plus difficile qu'une même expression faciale doit être interprétée différement selon le contexte.
Par exemple une personne peut pleurer parce qu'elle est triste mais aussi parce qu'elle est contente.
 
Certaines personnes pensent souvent à tord que les personnes avec autisme ne ressentent pas les émotions. Rien n'est plus faux.
Les personnes avec autisme ont souvent beaucoup d'empathie pour les gens.
Ce qui est difficile en revanche, est de mettre un mot sur les émotions.
De la même façon qu'identifier une expression du visage, associer un ressenti à un mot est souvent compliqué.
Beaucoup de personnes avec autisme répndent «&nbsp;je ne sais pas&nbsp;» si vous leur demander ce qu'elles ressentent.


<p>&nbsp;</p>
<div class="highlight">
<ol>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/qu-est-ce-que-l-autisme">Introduction - Qu'est-ce que l'autisme&nbsp;?</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/traitement-sensoriel">Traitement sensoriel</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/communication">Communication</a></li>
 <li>Langage non verbal</li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/socialisation">Socialisation</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/imprevus-anxiete-concentration">Imprévus, anxiété et concentration</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/capacites-et-potentiels">Capacités et potentiels</a></li>
</ol>
</div>





---
<small>Images issues de <a href="http://www.cygnification.com/" rel="nofollow">http://www.cygnification.com</a>, <a href="http://www.arasaac.org/" rel="nofollow">http://www.arasaac.org</a>.</small>

<script type="text/javascript">
  function eyes() {
    var canvas = document.getElementById('game_eyes');
    var ctx = canvas.getContext('2d');
    var refresh = 2000;
    var step = 150+25;
    var mouse = {'x': undefined, 'y': undefined};
    var cursor = 'default';
    var questions = [
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q1.jpg'; return i;}(), 'a': 0, 'p': ['Espiègle', 'Réconfortant', 'Irrité', 'Lassé'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q2.jpg'; return i;}(), 'a': 3, 'p': ['Terrifié', 'Arrogant', 'Agacé', 'Boulversé'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q3.jpg'; return i;}(), 'a': 2, 'p': ['Jovial', 'Troublé', 'Désireux', 'Confiant'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q4.jpg'; return i;}(), 'a': 1, 'p': ['Jovial', 'Insistant', 'Amusé', 'Détendu'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q5.jpg'; return i;}(), 'a': 2, 'p': ['Irrité', 'Sarcastique', 'Préoccupé', 'Accueillant'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q6.jpg'; return i;}(), 'a': 1, 'p': ['Hagard', 'Rêveur', 'Impatient', 'Alarmé'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q7.jpg'; return i;}(), 'a': 2, 'p': ['Remord', 'Accueillant', 'Mal à l\'aise', 'Découragé'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q8.jpg'; return i;}(), 'a': 0, 'p': ['Découragé', 'Soulagé', 'Timide', 'Excité'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q9.jpg'; return i;}(), 'a': 3, 'p': ['Agacé', 'Hostile', 'Horrifié', 'Préoccupé'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q10.jpg'; return i;}(), 'a': 0, 'p': ['Prudent', 'Insistant', 'Lassé', 'Hagard'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q11.jpg'; return i;}(), 'a': 2, 'p': ['Terrifié', 'Amusé', 'Remord', 'Charmeur'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q12.jpg'; return i;}(), 'a': 2, 'p': ['Indifférent', 'Embarrassé', 'Sceptique', 'Découragé'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q13.jpg'; return i;}(), 'a': 1, 'p': ['Décidé', 'Prudent', 'Menaçant', 'Timide'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q14.jpg'; return i;}(), 'a': 3, 'p': ['Irrité', 'Désappointé', 'Déprimé', 'Accusateur'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q15.jpg'; return i;}(), 'a': 0, 'p': ['Contemplatif', 'Troublé', 'Encourageant', 'Amusé'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q16.jpg'; return i;}(), 'a': 1, 'p': ['Irrité', 'Réfléchi', 'Encourageant', 'Amusé'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q17.jpg'; return i;}(), 'a': 0, 'p': ['Doutant', 'Affectueux', 'Espiègle', 'Hagard'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q18.jpg'; return i;}(), 'a': 0, 'p': ['Décidé', 'Amusé', 'Hagard', 'Lassé'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q19.jpg'; return i;}(), 'a': 3, 'p': ['Arrogant', 'Reconnaissant', 'Sarcastique', 'Séducteur'], 'o': 'none', c: 'none' },
      {'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/eyes/q20.jpg'; return i;}(), 'a': 1, 'p': ['Dominant', 'Accueillant', 'Coupable', 'Horrifié'], 'o': 'none', c: 'none' },
    ]
    shuffle_questions();

    var status = {'status': 'pause', 'interval': undefined};

    this.play = function() {
      if ( 'play' == status['status'])
        return;
      canvas.onmousemove = move;
      canvas.onclick = click;
      status['interval'] = setInterval(function() {
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

    function shuffle(a) {
      var j, x, i;
      for (i = a.length; i; i--) {
          j = Math.floor(Math.random() * i);
          x = a[i - 1];
          a[i - 1] = a[j];
          a[j] = x;
      }
    }
    function shuffle_questions() {
      shuffle(questions);
      questions = questions.slice(0, 6);
      for (i = 0; i < questions.length ; i++) {
        var p = questions[i]['p'].slice();
        var t = [0, 1, 2, 3];
        shuffle(t);
        questions[i]['a'] = t[questions[i]['a']];
        for (var j = 0 ; j < t.length ; j++) {
          questions[i]['p'][j] = p[t[j]];
        }
      }
    }
    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.fillStyle = "#e6c9b6";
      ctx.fillRect(0, 0, canvas.width, canvas.height);
      y = 0;
      for (var i = 0 ; i < questions.length; i++ ) {
        var img = questions[i]['img'];
        ctx.drawImage(img, (canvas.width/2) - (img.width / 2), y+10 );

        for (var j = 0 ; j < 4 ; j++ ) {
          if ( 'none' != questions[i]['c']) {
            if ( j == questions[i]['a'] ) {
              ctx.fillStyle = "#639f6b";
              ctx.fillRect((j*canvas.width/4) + 5, y+110, ((canvas.width/4))-10,50);
            } else if ( j == questions[i]['c'] && j != questions[i]['a']) {
              ctx.fillStyle = "#cc2936";
              ctx.fillRect((j*canvas.width/4) + 5, y+110, ((canvas.width/4))-10,50);
            }
            ctx.beginPath();
            ctx.rect((j*canvas.width/4) + 5, y+110, ((canvas.width/4))-10,50);
            ctx.stroke();
          } else {
            if ( j == questions[i]['o'] ) {
              ctx.fillStyle = "#8bd7f1";
              ctx.fillRect((j*canvas.width/4) + 5, y+110, ((canvas.width/4))-10,50);
            }
            ctx.beginPath();
            ctx.rect((j*canvas.width/4) + 5, y+110, ((canvas.width/4))-10,50);
            ctx.stroke();
          }
          ctx.font = "20px Arial";
          ctx.textAlign = "center";
          ctx.fillStyle = "#111";
          ctx.fillText(questions[i]['p'][j], ((j+1)*canvas.width/4) - canvas.width/8,y+110+30);
        }
        y += step;
      }
      canvas.style.cursor = cursor;
      return;
    }
    function click(e) {
      for (var i = 0 ; i < questions.length ; i++ ) {
        if ('none' != questions[i]['o'] && 'none' == questions[i]['c']) {
          questions[i]['c'] = questions[i]['o'];
          break;
        }
      }
      draw();
    }
    function move(e) {
      var r = canvas.getBoundingClientRect();
      mouse['x']=parseInt(e.clientX) - r.left;
      mouse['y']=parseInt(e.clientY) - r.top;
      y = 0;
      cursor = 'default';
      for (var i = 0 ; i < questions.length ; i++ ) {
        questions[i]['o'] = 'none';
        for (var j = 0; j < 4 ; j++) {
          if (
            ( mouse['x'] > (j*canvas.width/4) + 5 ) &&
            ( mouse['x'] < ((j*canvas.width/4) + 5) + ((canvas.width/4)-10)) &&
            ( mouse['y'] > y+110) &&
            ( mouse['y'] < y+110+50) && 
            ( questions[i]['c'] == 'none')
          ) {
            cursor = 'pointer';
            questions[i]['o'] = j;
            break;
          }
        }
        y += step;
      }
      draw();
    }
  }

  function isScrolledIntoView(el) {
    var elemTop = el.getBoundingClientRect().top;
    var elemBottom = el.getBoundingClientRect().bottom;

    var isVisible = ((elemTop >= 0) && (elemTop <= window.innerHeight)) || ((elemBottom >= 0) && (elemBottom <= window.innerHeight)) || ((elemTop < 0) && (elemBottom > window.innerHeight));
    return isVisible;
  }

  document.body.onload = function() {
    var canvas = [new eyes()];
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
