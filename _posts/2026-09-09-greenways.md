---
layout: post
title:  Greenwaying and Navier-Stokes
date:   2026-09-10 00:00-00
description: cycling on greenways and some other thoughts
tags: literature
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

<p> There's something melancholic about good bicycle infrastructure. Some kind of chilliness that comes with steel cities and modern architecture, or maybe something like a memory of the future, where we might enjoy green forests and bellowing lakes. Speaking of water, it would appear that as of September 8, 2026, the <a href = "https://www.quantamagazine.org/ai-has-solved-one-of-maths-1-million-millennium-prize-problems-20260908/">Navier-Stokes Millennium Prize problem</a> has been resolved, following <a href = "https://openai.com/index/navier-stokes-solution/">OpenAI's paper release</a>. This was to be expected, but it seems that <a href = "https://www.nytimes.com/2026/09/10/science/tristan-buckmaster-openai-math-navier-stokes.html">there are some uncertainties regarding attribution and proper credit</a> (sensationalized of course, but nevertheless informative), since OpenAI essentially tasked unregulated agents to piece together <i>anything</i>, not just things available in the literature. </p>

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/assets/img/lakeside4.jpg" alt="lake johnson">
    <figcaption>Lake Johnson in Raleigh</figcaption>
  </figure>
</div>

<p> <a href = "https://kirwinhampshire.substack.com/p/urgent-questions-for-mathematicians">Some people</a> are less than excited, and absolutely, I think such posts raise many valid concerns and questions that I have touched upon briefly before in passing. For instance, "Why do you <i>really</i> do mathematics?" has been asked before, and, really, it's a good question. I expect answers to vary widely, and it should be instinctive to ask one's advisor what they think. </p>

<p> Amidst the memes and funny posts about the resolution of Navier-Stokes—which, somehow, seems to be many people's first introduction to LLM-conducted mathematics research—there lies a deeper issue that genuinely threatens the field forever and makes me lose hope at an exponential rate. Strangely enough, this issue is something that can be controlled, at least to some extent. A collection of mathematicians (humans) created the <a href = "https://www.ahmath.org/">Association for Human Mathematics</a>, declaring that they would not use artificial intelligence in any work they conducted. The premise of the project is excellent: preserve humans in mathematics research. </p>

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/assets/img/lakeside3.jpg" alt="messenger bag">
    <figcaption>Another angle of Lake Johnson, with the trustworthy messenger bag</figcaption>
  </figure>
</div>

<p> Yet there's something sour here. Why do we do mathematics? To preserve our jobs? Or to live to see progress in a field to which we've dedicated our lives? I don't know the answer to this question, but I think some critical thought wouldn't immediately yield "as a researcher, we should never use artificial intelligence in any of our work." I firmly believe that those who do not use artificial intelligence are limiting their progress, and most likely they are hypocrites anyway. It was never about the impending doom of artificial intelligence. It was about whether the mathematics community could deal with a blow like this and recover. My belief is that if we continue our current trajectory of fearmongering and selfishness, there exists a threshold past which mathematics will never be able to recover. Perhaps a departure from <a href= "https://en.wikipedia.org/wiki/Luddites#External_links">Luddism</a> is warranted. The <a href = "https://leidendeclaration.ai/">Leiden Declaration</a> was an excellent start. In regard to public discourse, the declaration writes: </p>

> Mathematicians have a responsibility to support serious science journalism and to engage in public discourse to explain and contextualize artificial intelligence-assisted methods and results. This is particularly important for work within our own subfields, where specialized knowledge is required to assess claims about the depth, difficulty, and significance of results. Moreover, we encourage mathematicians to seek opportunities to cooperate with and support other researchers and creative professionals facing similar challenges.
>
> <br>
>
> — Leiden Declaration (2026)

<p> This is excellent. Good mathematical communication to the public is exactly what makes people care. After all, so much work done by contemporary mathematicians is so abstract that other mathematicians in slightly disjoint fields have trouble understanding things, much less a non-mathematician or layperson. However, appended to communication should be <i>education</i>. Mathematics is as much about education as it is about research. Have we really forgotten about our mentors? </p>

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/assets/img/lakeside5.jpg" alt="group cycle">
    <figcaption>The spectrum of cyclists</figcaption>
  </figure>
</div>

<p> Founding new declarations or organizations to further fragment the mathematical community might seem productive in the short-term, but in the long-term, it only increases the complexity of the community. If mathematicans are unable to unify over education, no future generation of mathematicians will be as curious as those before. "Would you like coming generations to be inspired to pursue mathematics?" Some will have to put down their pride and recognize that mathematics education is the pinnacle of the mathematics community, and without it there would be no researchers. </p>

<p> On the flip side, there is something about companies like OpenAI or Anthropic spending millions of dollars on tokens for agents to attempt to solve problems like Navier-Stokes that leaves me with many qualms. It seems entirely counter to human progress to rush mathematical discovery when it is so non-human. There is an excellent <a href = "https://www.youtube.com/watch?v=svl_1upFpQo">interview</a> with Terence Tao that deals with this, and Tao addresses, basically, the paradox of progress and significance. </p>

<p> Greenways really are nice. If we can incentivize car-centric American cities to construct greenways, why can't we incentivize mathematicians to be infinitely more community-oriented and build a program to face (but not fight against) the artificial intelligence problem? This is a long journey (after all, greenway infrastructure wasn't built in a day!), and we're just getting started. Godspeed. </p>
