---
layout: page
title:  "Mettez vous dans la peau d'une personne autiste - Communication"
permalink: /mettez-vous-dans-la-peau-d-une-personne-autiste/communication
hide_header_link: true
oembed_image: /assets/posts/2017-08-13/opengraph.png
---

La communication est essentielle pour exprimer ses besoins et ses émotions. Pourtant cela est une difficulté majeure chez beaucoup de personnes avec autisme.
Les personnes avec autisme peuvent être non verbales ou avoir un retard de langage avec un vocabulaire limité. 
Au contraire, certaines personnes peuvent parler correctement et avoir un large vocabulaire.

Les personnes non verbales peuvent utiliser d'autres moyens pour s'exprimer.
Certaines utilisent la langue des signes, ou peuvent utiliser des pictogrammes. 
Essayez de vous exprimer en utilisant des pictogrammes&nbsp;:
<!-- écriture pictogrammes (pecs) -->
<canvas id="game_pecs" width="700" height="400" style="border: 1px solid black; margin: 0 auto 0 auto; display: block;"></canvas>

D'autres encore peuvent s'exprimer en écrivant à l'aide d'un clavier ou en pointant les lettres écrites sur une feuille.
<!-- écriture en cliquant sur les lettres -->
<canvas id="game_writing" width="500" height="350" style="border: 1px solid black; margin: 0 auto 0 auto; display: block;"></canvas>

Comme vous avez pu le constater par vous-même, la difficulté est d'écrire rapidement. Imaginez que vous devez écrire chaque réponse aux questions que l'on vous pose oralement.
Imaginez que vous deviez réserver une chambre d'hôtel ou acheter un ticket de cinéma en écrivant tout ce que vous devez dire.

Chez les personnes verbales qui peuvent s'exprimer, certaines font de l'écholalie, c'est-à-dire peuvent répéter ce qu'elles entendent. Imaginez-vous
répéter la question que l'on vous pose au lieu d'y répondre.

De même, chez beaucoup de personnes avec autisme, comprendre les phrases imagées peut être difficile.
Par exemple lorsque nous *«&nbsp;racontons des salades&nbsp;»*, les personnes avec autisme peuvent réellement penser que nous parlons d'un légume.
Lorsque nous *«&nbsp;cassons les pieds&nbsp;»* de quelqu'un, nous ne l'empêchons pas de se déplacer. Nous utilisons tous les jours une quantité
importante d'expressions, généralement sans même nous en rendre compte.

Enfin, il vous est impossible de mentir. Lorsque quelqu'un vous demande comment vous trouvez ses nouveaux habits vous dites 
que cela ne lui va pas du tout.
Vous finissez par faire fuir le peu d'amis que vous avez réussis à vous faire.

<p>&nbsp;</p>
<div class="highlight">
<ol>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/qu-est-ce-que-l-autisme">Introduction - Qu'est-ce que l'autisme&nbsp;?</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/traitement-sensoriel">Traitement sensoriel</a></li>
 <li>Communication</li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/langage-non-verbal">Langage non verbal</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/socialisation">Socialisation</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/imprevus-anxiete-concentration">Imprévus, anxiété et concentration</a></li>
 <li><a href="/mettez-vous-dans-la-peau-d-une-personne-autiste/capacites-et-potentiels">Capacités et potentiels</a></li>
</ol>
</div>





---
<small>Images issues de <a href="http://www.cygnification.com/" rel="nofollow">http://www.cygnification.com</a>, <a href="http://www.arasaac.org/" rel="nofollow">http://www.arasaac.org</a>.</small>

<script type="text/javascript">
  function writing() {
    var canvas = document.getElementById('game_writing');
    var ctx = canvas.getContext('2d');
    var mouse = {'x': undefined, 'y': undefined};
    var cursor = 'default';
    var refresh = 1000;
    var background = new Image();
    background.src = '/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/writing/background.png';
    var alphabet_width = 7;
    var alphabet = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'];
    var sentences = [
      "J'aime le chocolat",
      "Je me sens triste",
      "Quand reviens-tu ?",
      "Je n'aime pas etre seul",
      "Le cours de maths etait difficile ce matin",
    ];
    var sentence = sentences[Math.floor((Math.random() * sentences.length))];
    var status = {'status': 'pause', 'interval': undefined};
    var state = {'hover': 'none', 'letters': []};

    this.play = function() {
      if ( 'play' == status['status'])
        return;
      canvas.onmousemove = move;
      canvas.onclick = click;
//      canvas.onmousedown = mousedown;
//      canvas.onmouseup = mouseup;
      status['interval'] = setInterval(function() {
        draw();
      }, refresh);
      
      status['status'] = 'play';
    }
    this.pause = function() {
      if ( 'pause' == status['status'])
        return;
      clearInterval(status['interval']);
      canvas.onmousemove = function(e) {}
      canvas.onclick = function(e) {}
//      canvas.onmousedown = function(e) {}
//      canvas.onmouseup = function(e) {}
      status['status'] = 'pause';
    }
    this.canvas = function() {
      return canvas;
    }
    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.drawImage(background, 0, 0, 600, 350);
      /* draw sentence */
      ctx.font = "25px Arial";
      ctx.textAlign = "left";
      ctx.fillStyle = "#111";
      x = (canvas.width - ctx.measureText(sentence).width)/2;
      var j = 0;
      for (var i = 0; i < sentence.length ; i++) {
        var char = sentence.charAt(i);
        if ( -1 == alphabet.indexOf(char.toUpperCase())) {
          ctx.fillStyle = "#111";
        } else {
          if (j >= state['letters'].length) {
            ctx.fillStyle = "#111";
          } else if (char.toUpperCase() == alphabet[state['letters'][j]]) {
            ctx.fillStyle = "#75aa3d";  
          } else {
            ctx.fillStyle = "#9e2127";
          }
          j += 1;
        }

        ctx.fillText(char, x, 40);
        x+= ctx.measureText(char).width;
      }

      /* draw alphabet */
      var y = 0;
      var j = 0;
      for (var i = 0 ; i < alphabet.length; i++) {
        if ((i%alphabet_width) == 0 && i != 0) {
          y += (canvas.width/alphabet_width);
          j = 0;
        }
        if (i == 21) {
          j += 1; // to center align the last row
        }
        ctx.fillStyle = '#ffffff';
        ctx.fillRect( (j*canvas.width/alphabet_width)+5, ((canvas.width/alphabet_width)-10)+y, (canvas.width/alphabet_width)-10, (canvas.width/alphabet_width)-10);
        ctx.beginPath();
        if (i == state['hover']) {
          ctx.strokeStyle="#4e97b2";
          ctx.lineWidth="3";
        } else {
          ctx.lineWidth="1";
          ctx.strokeStyle="#000000";
        }
        ctx.rect( (j*canvas.width/alphabet_width)+5, ((canvas.width/alphabet_width)-10)+y, (canvas.width/alphabet_width)-10, (canvas.width/alphabet_width)-10);
        ctx.stroke();
        ctx.font = "30px Arial";
        ctx.textAlign = "center";
        ctx.fillStyle = "#111";
        ctx.fillText(alphabet[i], (j*canvas.width/alphabet_width)+5 + (((canvas.width/alphabet_width)-10) / 2), ((canvas.width/alphabet_width)-10)+y+(((canvas.width/alphabet_width)-10) / 2));
//        ctx.drawImage(catalog[i]['img'], (j*canvas.width/alphabet_width)+5, 70+((canvas.width/alphabet_width)-10)+30+y,  (canvas.width/alphabet_width)-10, (canvas.width/alphabet_width)-10);
        j += 1;
      }
      canvas.style.cursor = cursor;
    }

    function what_is_under_mouse() {
      var y = 0;
      var j = 0;
      for (var i = 0 ; i < alphabet.length; i++) {
        if ((i%alphabet_width) == 0 && i != 0) {
          y += (canvas.width/alphabet_width);
          j = 0;
        }
        if (i == 21) {
          j += 1; // to center align the last row
        }
        if ( (mouse['x'] >= (j*canvas.width/alphabet_width)+5) && (mouse['x'] <= ((j*canvas.width/alphabet_width)+5)+((canvas.width/alphabet_width)-10)) && (mouse['y'] >= ((canvas.width/alphabet_width)-10)+y) && (mouse['y'] <= (((canvas.width/alphabet_width)-10)+y) + ((canvas.width/alphabet_width)-10)) ) {
          return {'where': 'alphabet', 'which': i};
        }
        j += 1;
      }
      return {'where': 'nowhere'};
    }
    function move(e) {
      var r = canvas.getBoundingClientRect();
      mouse['x']=parseInt(e.clientX) - r.left;
      mouse['y']=parseInt(e.clientY) - r.top;
      var c = what_is_under_mouse()
      if (c['where'] == 'alphabet') {
        state['hover'] = c['which'];
        cursor = 'pointer';
      } else {
        state['hover'] = 'none';
        cursor = 'default';
      }
      draw();
    }
    function click(e) {
      var r = canvas.getBoundingClientRect();
      mouse['x']=parseInt(e.clientX) - r.left;
      mouse['y']=parseInt(e.clientY) - r.top;
      var c = what_is_under_mouse()
      if (c['where'] == 'alphabet') {
        state['letters'].push(c['which']);
      }
      draw();
    }
  }
  function pecs() {
    var canvas = document.getElementById('game_pecs');
    var ctx = canvas.getContext('2d');
    var mouse = {'x': undefined, 'y': undefined};
    var cursor = 'default';
    var nb_words = 6;
    var nb_catalog = 10;
    var refresh = 1000;
    var clicked = false;
    var state = {'dragged': 'none', 'hover': 'none', 'sentence': []};
    var catalog = [
      {'word': 'je', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/je.png'; return i;}(), 'selected': false },
      {'word': 'tu', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/tu.png'; return i;}(), 'selected': false },
      {'word': 'qui', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/qui.png'; return i;}(), 'selected': false },

      {'word': 'un', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/un.png'; return i;}(), 'selected': false },
      {'word': 'bonbon', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/bonbon.png'; return i;}(), 'selected': false },

      {'word': 'parc', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/parc.png'; return i;}(), 'selected': false },

      {'word': 'aller', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/aller.png'; return i;}(), 'selected': false },
      {'word': 'manger', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/manger.png'; return i;}(), 'selected': false },
      {'word': 'coucher', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/coucher.png'; return i;}(), 'selected': false },
      {'word': 'aimer', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/aimer.png'; return i;}(), 'selected': false },
      {'word': 'lire', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/lire.png'; return i;}(), 'selected': false },
      {'word': 'venir', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/venir.png'; return i;}(), 'selected': false },
      {'word': 'voir', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/voir.png'; return i;}(), 'selected': false },
      {'word': 'ecouter', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/ecouter.png'; return i;}(), 'selected': false },
      {'word': 'promener_le_chien', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/promener_le_chien.png'; return i;}(), 'selected': false },


      {'word': 'dans', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/dans.png'; return i;}(), 'selected': false },
      {'word': 'quand', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/quand.png'; return i;}(), 'selected': false },
      {'word': 'demain', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/demain.png'; return i;}(), 'selected': false },

      {'word': 'question', 'img': function(){var i = new Image(); i.src='/assets/pages/mettez-vous-dans-la-peau-d-une-personne-autiste/pecs/question.png'; return i;}(), 'selected': false },
    ];
    var sentences = [
      {'sentence': 'Je veux manger un bonbon.', 'pictos': ['je', 'manger', 'un', 'bonbon']},
      {'sentence': 'Je veux aller au parc.', 'pictos': ['je', 'aller', 'parc']},
      {'sentence': 'Je t\'aime!', 'pictos': ['je', 'aimer']},
      {'sentence': 'Peux-tu me lire une histoire ?', 'pictos': ['tu', 'lire', 'question']},
      {'sentence': 'Je promène le chien dans le parc.', 'pictos': ['promener_le_chien', 'dans', 'parc']},
      {'sentence': 'À quelle heure mange-t-on ?', 'pictos': ['quand', 'manger', 'question']},
      {'sentence': 'Va-t-on au parc demain ?', 'pictos': ['aller', 'parc', 'demain', 'question']},
      {'sentence': 'Je veux partir.', 'pictos': ['je', 'aller']},
      {'sentence': 'Qui viens demain ?', 'pictos': ['qui', 'venir', 'demain', 'question']},
      {'sentence': 'Tu viens ?', 'pictos': ['tu', 'venir', 'question']},
      {'sentence': 'Quand viens-tu ?', 'pictos': ['quand', 'venir', 'tu', 'question']},
      {'sentence': 'Qui viens au parc avec moi ?', 'pictos': ['qui', 'aller', 'parc', 'je', 'question']},
      {'sentence': 'Je vais au lit.', 'pictos': ['je', 'coucher']},
      {'sentence': 'Je t\'ai vu au parc.', 'pictos': ['je', 'voir', 'tu', 'parc']},
      {'sentence': 'Je t\'écoute quand tu parles.', 'pictos': ['je', 'ecouter', 'tu']},
      {'sentence': 'J\'entends quelque chose.', 'pictos': ['je', 'ecouter']},
      {'sentence': 'Quand mange-t-on ?', 'pictos': ['quand', 'manger', 'questions']},
      {'sentence': 'Je veux lire dans le parc.', 'pictos': ['je', 'lire', 'dans', 'parc']},
    ];
    var sentence = Math.floor((Math.random() * sentences.length));
    for (var i = 0; i < sentences[sentence]['pictos'].length ; i++) {
      state['sentence'].push(undefined);
    }

    var status = {'status': 'pause', 'interval': undefined};
    this.play = function() {
      if ( 'play' == status['status'])
        return;
      canvas.onmousemove = move;
      canvas.onmousedown = mousedown;
      canvas.onmouseup = mouseup;
      status['interval'] = setInterval(function() {
        draw();
      }, refresh);
      
      status['status'] = 'play';
    }
    this.pause = function() {
      if ( 'pause' == status['status'])
        return;
      clearInterval(status['interval']);
      canvas.onmousemove = function(e) {}
      canvas.onmousedown = function(e) {}
      canvas.onmouseup = function(e) {}
      status['status'] = 'pause';
    }
    this.canvas = function() {
      return canvas;
    }
    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      ctx.font = "30px Arial";
      ctx.textAlign = "center";
      ctx.fillStyle = "#111"
      ctx.fillText(sentences[sentence]['sentence'], canvas.width/2, 50);

      /* draw sentence */
      for (var i = 0; i < sentences[sentence]['pictos'].length ; i++) {
        if ( sentences[sentence]['pictos'].length == nb_words) {
          var x = (i*canvas.width/nb_words) +5;
        } else {
          var x =  (i+1)*((canvas.width)/(sentences[sentence]['pictos'].length+1)) - ((canvas.width/nb_words)/2)
        }
        if ( undefined == state['sentence'][i]) {
          ctx.beginPath();
          ctx.lineWidth="1";
          ctx.strokeStyle="#000000";
        } else if (sentences[sentence]['pictos'][i] == catalog[state['sentence'][i]]['word']) {
          ctx.beginPath();
          ctx.lineWidth="5";
          ctx.strokeStyle="#75aa3d";
        } else {
          ctx.beginPath();
          ctx.lineWidth="5";
          ctx.strokeStyle="#9e2127";
        }
        ctx.rect(x, 70, (canvas.width/nb_words)-10, (canvas.width/nb_words)-10);
        ctx.stroke();
        if (undefined != state['sentence'][i]) {
          ctx.drawImage(catalog[state['sentence'][i]]['img'], x, 70, (canvas.width/nb_words)-10, (canvas.width/nb_words)-10);
        }
      }


      /* draw catalog */
      var y = 0;
      var j = 0;
      for (var i = 0 ; i < catalog.length; i++) {
        if ((i%nb_catalog) == 0) {
          y += (canvas.width/nb_catalog);
          j = 0;
        }
        ctx.beginPath();
        if (i == state['hover'] && false == catalog[i]['selected']) {
          ctx.strokeStyle="#4e97b2";
          ctx.lineWidth="3";
        } else {
          ctx.strokeStyle="#000000";
          ctx.lineWidth="1";
        }
        ctx.rect( (j*canvas.width/nb_catalog)+5, 70+((canvas.width/nb_catalog)-10)+30+y, (canvas.width/nb_catalog)-10, (canvas.width/nb_catalog)-10);
        ctx.stroke();
        ctx.drawImage(catalog[i]['img'], (j*canvas.width/nb_catalog)+5, 70+((canvas.width/nb_catalog)-10)+30+y,  (canvas.width/nb_catalog)-10, (canvas.width/nb_catalog)-10);
        if (true == catalog[i]['selected']) {
          ctx.fillStyle = "rgba(255, 255, 255, 0.7)";
          ctx.fillRect((j*canvas.width/nb_catalog)+5, 70+((canvas.width/nb_catalog)-10)+30+y,  (canvas.width/nb_catalog)-10, (canvas.width/nb_catalog)-10);
        }
        j += 1;
      }

      /* if something dragged, draw the content dragged under the mouse */
      if ('none' != state['dragged']) {
        ctx.drawImage(catalog[state['dragged']]['img'], mouse['x'] - (((canvas.width/nb_catalog)-10)/2), mouse['y'] - (((canvas.width/nb_catalog)-10)/2), (canvas.width/nb_catalog)-10, (canvas.width/nb_catalog)-10);
      }
      canvas.style.cursor = cursor;

    }

    function what_is_under_mouse() {
      if ( mouse['y'] >= 70 && mouse['y'] <= 70+((canvas.width/nb_words)-10) ) {
        for (var i = 0; i < sentences[sentence]['pictos'].length ; i++) {
          if ( sentences[sentence]['pictos'].length == nb_words) {
            var x = (i*canvas.width/nb_words) +5;
          } else {
            var x =  (i+1)*((canvas.width)/(sentences[sentence]['pictos'].length+1)) - ((canvas.width/nb_words)/2)
          }
          if (mouse['x'] >= x && mouse['x'] <= x+((canvas.width/nb_words)-10)) {
            return {'where': 'sentence', 'which': i};
          }
        }
        return {'where': 'nowhere'};
      } else {
        var y = 0;
        var j = 0;
        for (var i = 0 ; i < catalog.length; i++) {
          if ((i%nb_catalog) == 0) {
            y += (canvas.width/nb_catalog);
            j = 0;
          }
          ctx.drawImage(catalog[i]['img'], (j*canvas.width/nb_catalog)+5, 70+((canvas.width/nb_catalog)-10)+30+y,  (canvas.width/nb_catalog)-10, (canvas.width/nb_catalog)-10);
          if ( (mouse['x'] >= (j*canvas.width/nb_catalog)+5) && (mouse['x'] <= ((j*canvas.width/nb_catalog)+5)+((canvas.width/nb_catalog)-10)) && (mouse['y'] >= 70+((canvas.width/nb_catalog)-10)+30+y) && (mouse['y'] <= (70+((canvas.width/nb_catalog)-10)+30+y) + ((canvas.width/nb_catalog)-10)) ) {
            return {'where': 'catalog', 'which': i};
          }
          j += 1;
        }
        return {'where': 'nowhere'};
      }
    }

    function mousedown(e) {
      var r = canvas.getBoundingClientRect();
      mouse['x']=parseInt(e.clientX) - r.left;
      mouse['y']=parseInt(e.clientY) - r.top;

      clicked = true;

      var c = what_is_under_mouse()
      if ('catalog' == c['where'] && false == catalog[c['which']]['selected'] ) {
        cursor = 'move';
        state['dragged'] = c['which'];
        catalog[c['which']]['selected'] = true;
      } else if ('sentence' == c['where'] && undefined != state['sentence'][c['which']]) {
        cursor = 'move';
        state['dragged'] = state['sentence'][c['which']];
        clicked = {'sentence': c['which'], 'picto':  state['sentence'][c['which']]};
        state['sentence'][c['which']] = undefined;
      }
    }
    function mouseup(e) {
      var c = what_is_under_mouse()
      if ('sentence' == c['where']) {
        if ( clicked['sentence'] == c['which']) {
          catalog[clicked['picto']]['selected'] = false;
          state['sentence'][c['which']] = undefined;
          draw();
        } else {
          if ('none' != state['dragged']) {
            if ( undefined != state['sentence'][c['which']] ) {
              catalog[state['sentence'][c['which']]]['selected'] = false;
            }
            state['sentence'][c['which']] = state['dragged'];
          }
        }
      } else {
        if ( 'none' != state['dragged']) {
          catalog[state['dragged']]['selected'] = false;
        }
      }
      state['dragged'] = 'none';
      if ((c['where'] == 'catalog') || (c['where'] == 'sentence' && undefined != state['sentence'][c['which']])) {
        cursor = 'pointer';
      } else {
        cursor = 'default';
      }
      clicked = false;
      draw();
    }

    function move(e) {
      var r = canvas.getBoundingClientRect();
      mouse['x']=parseInt(e.clientX) - r.left;
      mouse['y']=parseInt(e.clientY) - r.top;
      var c = what_is_under_mouse()
      if ('none' != state['dragged']) {
        cursor = 'move';
      } else {
        if ((c['where'] == 'catalog') || (c['where'] == 'sentence' && undefined != state['sentence'][c['which']])) {
          cursor = 'pointer';
          if (c['where'] == 'catalog') {
            state['hover'] = c['which'];
          } else {
            state['hover'] = 'none';
          }
        } else {
          cursor = 'default';
          state['hover'] = 'none';
        }
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
    var canvas = [new pecs(), new writing()];
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
