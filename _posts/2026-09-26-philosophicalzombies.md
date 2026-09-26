---
layout: post
title:  Philosophical Zombies and Selfish Introspection
date:   2026-09-26 00:00-00
description: how to keep our sanity
tags: literature mathematics
---

<style>
  /* ==========================================================================
     1. SHARED CARD & CAPTION BASE STYLES
     ========================================================================== */
  .grid-card {
    margin: 0;
    position: relative;
    overflow: hidden;
    border-radius: 8px;
    background-color: #f7f7f7;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
    width: 100%;
  }

  .grid-card img {
    width: 100%;
    display: block;
    object-fit: cover;
  }

  .grid-card figcaption {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    padding: 35px 15px 12px 15px;
    color: #ffffff;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    font-size: 14px;
    font-weight: 500;
    background: linear-gradient(transparent, rgba(0, 0, 0, 0.85));
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.6);
    pointer-events: auto; 
    z-index: 2;
  }

  .grid-card figcaption a {
    pointer-events: auto;
  }

  /* ==========================================================================
     2. CONTAINER LAYOUT TYPES (BASE STYLES)
     ========================================================================== */
  
  /* Layout A: The 2x2 Image Grid Container */
  .mobile-friendly-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
    gap: 12px;
    max-width: 1000px;
    margin: 20px auto;
    padding: 10px;
    box-sizing: border-box;
  }

  /* Layout B: Asymmetrical Grid (Wider Left, Narrower Right, Full Bottom) */
  .triple-image-grid {
    display: grid;
    grid-template-columns: 1.3fr 0.7fr;
    gap: 12px;
    max-width: 1000px;
    margin: 20px auto;
    padding: 10px;
    box-sizing: border-box;
    align-items: stretch;
  }

  /* Layout C: Standalone Single Image Container */
  .standalone-image-container {
    max-width: 1000px;
    margin: 25px auto;
    padding: 0 10px;
    box-sizing: border-box;
  }

  /* Layout D: The 2-Image Portrait Grid Container */
  .dual-portrait-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
    max-width: 1000px;
    margin: 20px auto;
    padding: 10px;
    box-sizing: border-box;
  }

  /* Layout E: 3-Image Grid (Full Width Top, 2 Equal Columns Bottom) */
  .top-heavy-triple-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
    max-width: 1000px;
    margin: 20px auto;
    padding: 10px;
    box-sizing: border-box;
  }

  /* Layout G: Bottom-Heavy 3-Image Grid (2 Portraits Top, 1 Full Landscape Bottom) */
  .bottom-heavy-triple-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
    max-width: 1000px;
    margin: 20px auto;
    padding: 10px;
    box-sizing: border-box;
  }

  /* Layout I: Standalone Side-by-Side Dual Landscape Grid (No Cropping) */
  .dual-landscape-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
    max-width: 1000px;
    margin: 20px auto;
    padding: 10px;
    box-sizing: border-box;
    align-items: stretch;
  }

  /* Layout J: Fixed Bounded Asymmetric Diagram Pair */
  .asymmetric-clearance-grid {
    display: grid;
    grid-template-columns: 1.15fr 0.85fr;
    gap: 12px;
    max-width: 1000px;
    margin: 20px auto;
    padding: 10px;
    box-sizing: border-box;
    align-items: stretch;
  }

  /* Grid cell helper: Spans an item full width across 2 columns */
  .full-width-row {
    grid-column: span 2;
  }

  /* ==========================================================================
     3. DESKTOP RESPONSIVE CONTROL (Screen width > 768px)
     ========================================================================== */
  @media (min-width: 769px) {
    /* Layout A (2x2 Grid) */
    .mobile-friendly-grid { grid-template-columns: repeat(2, 1fr); }
    .mobile-friendly-grid .landscape-img img { height: 380px; }
    .mobile-friendly-grid .portrait-img img { height: 550px; }
    
    /* Layout B (Asymmetrical Grid) */
    .triple-image-grid .landscape-img img { height: auto; }
    .triple-image-grid .portrait-img { display: flex; }
    .triple-image-grid .portrait-img img { height: 100%; } 
    .triple-image-grid .full-width-row img { height: 440px; }

    /* Layout C (Standalone Image) */
    .standalone-image-container .landscape-img img { height: 480px; } 
    
    /* Layout D (Dual Portrait) */
    .dual-portrait-grid .portrait-img img { height: 600px; }

    /* Layout E (Top-Heavy Grid) */
    .top-heavy-triple-grid .full-width-row img { height: 450px; }
    .top-heavy-triple-grid .portrait-img img { height: 580px; }

    /* Layout G (Bottom-Heavy Grid) */
    .bottom-heavy-triple-grid .portrait-img img { height: 550px; }
    .bottom-heavy-triple-grid .full-width-row img { height: 420px; }

    /* Layout I (Standalone Dual Landscape Fix) */
    .dual-landscape-grid .landscape-img img { height: 360px; }

    /* Layout J (Asymmetric Diagram Desktop Bounds Fixed) */
    .asymmetric-clearance-grid .left-diagram,
    .asymmetric-clearance-grid .right-cropped-board {
      height: 450px; /* Locks container height perfectly */
    }
    .asymmetric-clearance-grid .left-diagram {
      background-color: #ffffff;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .asymmetric-clearance-grid .left-diagram img {
      height: 100%;
      width: auto; /* Scales proportionally horizontally without layout overflow */
      object-fit: contain;
    }
    .asymmetric-clearance-grid .right-cropped-board img {
      height: 100%;
      object-fit: cover; /* Crops sides cleanly to flush match diagram height */
    }
  }

  /* Layout K: Uncropped Panoramic Banner (For ultra-wide aspect ratios) */
  .panoramic-image-container {
    max-width: 1000px;
    margin: 25px auto;
    padding: 0 10px;
    box-sizing: border-box;
  }

  .panoramic-image-container .panorama-img img {
    width: 100%;
    height: auto !important; /* Preserves exact native aspect ratio without zooming in */
    object-fit: contain !important;
  }

  /* ==========================================================================
     4. MOBILE RESPONSIVE CONTROL (Screen width <= 768px)
     ========================================================================== */
  @media (max-width: 768px) {
    .mobile-friendly-grid, 
    .triple-image-grid,
    .dual-portrait-grid,
    .top-heavy-triple-grid,
    .bottom-heavy-triple-grid,
    .dual-landscape-grid,
    .asymmetric-clearance-grid {
      grid-template-columns: 1fr;
      gap: 16px;
    }
    
    .full-width-row {
      grid-column: span 1; 
    }
    
    .landscape-img img, 
    .full-width-row img,
    .asymmetric-clearance-grid .right-cropped-board img { 
      height: 240px; 
    }
    
    .portrait-img img { 
      height: 420px; 
    }

    .asymmetric-clearance-grid .left-diagram img {
      height: auto;
      object-fit: contain;
      background-color: #ffffff;
    }
    
    .grid-card figcaption { 
      font-size: 13px; 
    }
  }
</style>


<p> In these <a href = "https://openai.com/index/advisory-group-on-mathematics-and-ai/">changing times</a>, it's difficult to simultaneously be a mathematician and a non-complaining person. Complaining, hating society, blaming the world—these are all excellent retreats from reality. This isn't to say those are incorrect. Fundamentally, they are largely why we face problems. In our introspection, we behave like selfish <a href = "https://en.wikipedia.org/wiki/Solipsism">solipsists</a>, describing how we are being infinitely wronged by the people, the weather, the government (this might have some validity), the mosquitoes, the constant of feeling lost, the perenially blooming eczema, the slight over-moisturization of my fingers on the violin fingerboard, the periodically loosening screw mechanism within my mechanical pencil that causes inexplicable breakages at important moments, and so on. We think these things only because we think, and we take that as evidence that we are being wronged by everything that is not ourselves. Everything and everyone else is a barrier to individual progress, whatever that means, if that even is the goal. </p>

<p> I recently came across, in a course, the term <a href = "https://en.wikipedia.org/wiki/Philosophical_zombie">philosophical zombie</a>, a theoretical living organism that behaves exactly like one yet is unable to <i>think</i>, at least in the sense that it does not feel nor does it experience—it only acts and reacts. It almost feels as though humanity is converging more and more toward an enormous commune of philosophical zombies—not because we do not think or have some kind of phenomenal experience, but because what we perceive and believe we feel is becoming increasingly manufactured and infected by the philosophical zombies who now pulsate through the world. How can we prove to ourselves that we aren't philosophical zombies? Complaining about artificial intelligence in mathematics is the natural thing to do, and yes, I care about getting a job in the future, but it seems so petty in the grand scheme. I'm tired of complaining. </p>

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/assets/img/algtop1.jpg" alt="algebraic topology board">
    <figcaption>Some DRP chalk board notes on <a href = "https://en.wikipedia.org/wiki/Simplicial_complex">simplicial complexes</a> and simplicial homology</figcaption>
  </figure>
</div>

<p> I spoke to my mentor and graduate student friend in the 4th year of his PhD, and his prospects appear rather bleak—the academia pipeline, modulo the intrisic competitiveness and difficulty in the field, now reveals the impossibility of achieving a reasonable research career in the midst of AI. After a PhD, the natural next step is to apply for postdoc positions, then for tenure track professorship positions. I think he recognizes very clearly this struggle. Why do you do mathematics? Again, this question comes about. <a href = "https://en.wikipedia.org/wiki/G._H._Hardy">G.H. Hardy</a> probably gave an eloquent answer about braving the unknowns of mathematics alone yet with a kind of intense determination and self-confidence, and, from this, perhaps an emergent sense of self-identity and service toward the pinnacles of humanity and human achievement. Perhaps Hardy was onto something, but the only answer to that question is really: "I am selfish." </p>

<p> Is that really such a bad thing, anyway? Does humanity have an obligation to be in service of its future? Its past? Society may criticise artists, musicians, and general creatives for being generally unhelpful for the technological advancement of humanity, yet there exists an intrinsic recognition that there is tangible value to creation, emotion, beauty, <a href = "https://www.merriam-webster.com/dictionary/mellifluous">mellifluousness</a>, and so on. Perhaps this is where humanity has an obligation to be in service of its present. </p>

<p> Yet something like this is inconvenient. It takes time. Take board games for example. As a semi-pseudo enjoyer of board games, why should I move pieces around a board and manually keep track of multiple moving parts if I could digitize the entire scheme and forget about the tedium? </p>

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/assets/img/hf4ss.jpg" alt="High Frontier 4 all gameplay">
    <figcaption>Yes, I spent several hours moving a few small pieces of plastic and wood 75 centimetres away from their original position (<a href = "https://boardgamegeek.com/boardgame/281655/high-frontier-4-all">HF4A</a>)</figcaption>
  </figure>
</div>

<p> As a violinist, why do I care about the tediousness of violin technique and accuracy when, theoretically, I will never be as good as the masters? </p>

<p> Perhaps a deeper question revolves about trying to reconcile our own recognition of mediocrity with the looming existence of non-mediocrity. Why do we do anything if we will never be the best at it? In mathematics particularly, it is infinitesimally likely that neither I, my graduate friend, nor my younger professors, will obtain something like a Fields medal. </p>

<p> So how does this discussion fit into the broader discussion of artificial intelligence and mathematics? Well, it shows that we are pre-assuming a notion of novelty in mathematics and reacting to artificial intelligence retroactively. I maintain again that the real novelty of mathematics is the fact that we can be excited about teaching mathematics to people, not necessarily in extending further. So many mathematical theories and ideas go untaught and untouched—exclusivity might entertain some, but should a selfish mathematician not proudly proclaim "I want everyone to know about this theory!"? The gap between PhD theses and frontier mathematics research is now as large as ever, and artificial intelligence, compounded with the wrong kind of selfishness, has created an illusion of desperation. Another declaration, signed by a collection of Fields medalists, addresses the issue of students directly: </p>

> The mathematical community functions, in many ways, as a miniature version of humanity. It consists of individuals using a wide variety of different approaches, joined by core values. The most precious resources of our profession are students and ideas, and these we nurture with great care. We feel responsible to let them grow to their full potential, until they can live a life of their own in the mathematical world. For students we often suggest problems with the core intention of developing skills making them well-positioned for advances in research and elsewhere.
>
> <br>
>
> — <a href = "https://mathandai.org/">A Severe Misalignment of AI in Mathematics</a> (2026)

<p> Are we really running out of time? Assuming that the <a href = "https://en.wikipedia.org/wiki/AI_alignment">AI alignment</a> problem raises enough concern such that humanity decides to give itself some room to breathe, the ruins of mathematics will still take time to rebuild. Let us bridge the gap. Perhaps, in the meantime, we should focus on what makes us happy and feel human, like playing the violin or board games or spending hours thinking. Just to keep our sanity. </p>

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/assets/img/uncarboretum.jpg" alt="UNC arboretum">
    <figcaption><a href = "https://ncbg.unc.edu/visit/coker-arboretum/">Coker Arboretum</a></figcaption>
  </figure>
</div>

<p> It's strange. So much internal turmoil and self-reflection on a career that may not even exist in five years. And yet autumn still comes about. The leaves haven't changed yet in Chapel Hill, but there's a nod toward gradually dimming sunshine in the evenings. The temperature has become cooler (with occasional periods of hot humid air). <i>Sigh.</i> </p>
