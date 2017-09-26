---
layout: page
title:  Mettez vous dans la peau d'une personne autiste
permalink: /mettez-vous-dans-la-peau-d-une-personne-autiste/imprevus-anxiete-concentration
hide_header_link: true
oembed_image: /assets/posts/2017-08-13/opengraph.png
---

# Imprévus

Pour vivre dans un monde totalement imprévisible avec un environnement difficilement supportable, rien de mieux que de s'appliquer à suivre une routine quotidienne, des rituels.
C'est votre «&nbsp;pilote automatique&nbsp;» qui vous évite de réfléchir aux actions habituelle que vous devez réaliser. Toutefois, il arrive que la routine ne se déroule pas comme prévu et qu'un événement se produise de façon inopinée.

Vous devez alors reprendre le «&nbsp;pilotage manuel&nbsp;» ce qui vous demande beaucoup d'énergie et d'efforts.
Vous vous demandez alors ce qu'il va arriver. Vous essayez de prévoir des dizaines de scénarios de tout ce qui pourrait vous arriver. Cela fini par vous dépasser complètement,
génère du énormément de stress et vous fini par vous épuiser. 



# Anxiété

En tant que personne avec autisme, si l'on vous demande en quoi l'autisme vous handicape-t-il au quotidien, vous avez
de grande chance de parler de l'anxiété.
Vivre dans un environnement hostile dans lequel vous ne savez pas comment faire pour communiquer, socialiser avec les autres personnes vous est très difficile. À force d'être 
déçu des erreurs que vous avez pu faire (par exemple, vous n'avez pas réussi à vous expliquer correctement) et à cause du regard des gens, vous devenez anxieux.

Vous n'osez plus aller vers les gens, voire même de sortir de chez vous.
Vous ne parlez que lorsque cela est vraiment nécessaire.
Finalement, vous restez dans la solitude.

Comme le dit très bien le docteur Tony Attwood, les personnes avec autisme sont spécialistes lorsqu'il s'agit de devenir inquiet&nbsp;!

# Problèmes de concentration

Beaucoup de personnes avec autisme ont également du mal à rester concentrer, voire même de rester assis pendant de longues périodes.
Lorsqu'un sujet ne vous intéresse pas, il est impossible de vous faire travailler sur celui-ci car cela demande une concentration trop importante.
Pour vous donner une idée, c'est comme-ci vous deviez dire de quelle couleur est écrit chacun des mots suivants&nbsp;:

<!-- lire les couleurs écrites dans une autre couleur -->
<canvas id="game_colour" width="700" height="300" style="border: 1px solid black; margin: 0 auto 0 auto; display: block;"></canvas>

---

<script type="text/javascript">
  function colour() {
    var canvas = document.getElementById('game_colour');
    var ctx = canvas.getContext('2d');
    var nb = [4, 5];
    var step = 75;
    var colors = [{'t': 'Orange', 'h': '#e18335'}, {'t': 'Bleu', 'h': '#478aa2'}, {'t': 'Vert', 'h': '#5e8831'}, {'t': 'Rouge', 'h': '#ff0000'}, {'t': 'Noir', 'h': '#000000'}, {'t': 'Rose', 'h': '#ff6282'}, {'t': 'Jaune', 'h': '#d0ba32'}, {'t': 'Violet', 'h': '#733ab7' }, {'t': 'Blanc', 'h': '#441151'}, {'t': 'Gris', 'h': '#9c9687'}, {'t': 'Bleu', 'h': '#2d93ad'}, {'t': 'Jaune', 'h': '#dfd25a'}, {'t': 'Rose', 'h': '#ca61c3'}, {'t': 'Rouge', 'h': '#ef233c'}, {'t': 'Violet', 'h': '#631a86' }, {'t': 'Orange', 'h': '#e4572e'}, {'t': 'Vert', 'h': '#b9cb83'}]
    var drawn = false;
    var status = {'status': 'pause', 'interval': undefined};

    this.play = function() {
      if ( 'play' == status['status'])
        return;
      if ( false == drawn )
        draw();
      status['status'] = 'play';
    }
    this.pause = function() {
      if ( 'pause' == status['status'])
        return;
      status['status'] = 'pause';
    }
    this.canvas = function() {
      return canvas;
    }

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      var y = 0;
      for (var i = 0; i < nb[0] ; i++) {
        for (var j = 0; j < nb[1] ; j++) {
          var color_t = Math.floor((Math.random() * colors.length));
          var color_h = Math.floor((Math.random() * colors.length));
//          ctx.rect( (j*canvas.width/nb[1])+5, y+10, (canvas.width/nb[1])-10, 50);
//          ctx.stroke();
          ctx.font = "30px Arial";
          ctx.textAlign = "center";
          ctx.fillStyle = colors[color_h]['h'];
          ctx.fillText(colors[color_t]['t'], ((j+1)*canvas.width/nb[1]) - ((canvas.width/nb[1])/2), y+45);
        }
        y += step;
      }
      drawn = true;
    }
  }
  function isScrolledIntoView(el) {
    var elemTop = el.getBoundingClientRect().top;
    var elemBottom = el.getBoundingClientRect().bottom;

    var isVisible = ((elemTop >= 0) && (elemTop <= window.innerHeight)) || ((elemBottom >= 0) && (elemBottom <= window.innerHeight)) || ((elemTop < 0) && (elemBottom > window.innerHeight));
    return isVisible;
  }



  document.body.onload = function() {
    var canvas = [new colour()];
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

