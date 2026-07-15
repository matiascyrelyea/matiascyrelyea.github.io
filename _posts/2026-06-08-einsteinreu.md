---
layout: post
title:  Einstein Institute of Mathematics REU
date:   2026-07-15 00:00-00
description: happenings for summer 2026
tags: mathematics research
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


<nav>
  <ul>
    <li><a href="#0">8 June, 2026</a></li>
    <li><a href="#1">11 June,  2026</a></li>
    <li><a href="#2">14 June, 2026</a></li>
    <li><a href="#3">26 June, 2026</a></li>
    <li><a href="#4">28 June, 2026</a></li>
    <li><a href="#5">3 July, 2026</a></li>
    <li><a href="#6">10 July, 2026</a></li>
    <li><a href="#7">12 July, 2026</a></li>
  </ul>
</nav>

<h5 id="0">(8 June, 2026)</h5>
<p> This summer I am attending the Einstein Institute of Mathematics REU in Jerusalem, Israel. The program just began as of 8 June, so I will add many experiences and some pictures to this post as more things happen, but I'd like to start here by sort of describing the beginning of the program and some things I've experienced so far. </p>

<p> The elephant in the room at this current moment is the reality of long-standing geopolitical conflict in the region. I won't talk about details or politics as my goal here is to document my experiences, but the program began rather explosively with sirens, missile alerts, and a video of a missile being intercepted. More details <a href="https://www.aljazeera.com/video/newsfeed/2026/6/8/missiles-intercepted-over-occupied-east-jerusalem-and-west-bank-2">here</a>. This didn't really hinder much. </p>

<p> I was able to meet with my advisor, Dr. Shai Evra, and the project was broadly introduced to us. From what I currently understand, a large fragment of the REU is dedicated to understanding the <a href = "https://en.wikipedia.org/wiki/Solovay%E2%80%93Kitaev_theorem">Solovay-Kitaev theorem</a> for compact Lie groups, and potentially attempting to extend the algorithm to general groups. Depending on the direction, we might also attempt to work on an open problem in group theory, or possibly go in some other directions relating to quantum algorithms and algebraic number theory. I imagine objectives and interests will shift, but this is the basic skeleton of the program. </p>

<p> I've also had a lot of fun meeting the other people in the program, and it's nice to see how international our group is! We have people from China, South Korea, Greece, and the United States. </p>

<p> Anyway, some of us visited the campus today, and I have to say: the Hebrew University has a rather nice campus, and I really appreciate the combination of traditional and brutalist architecture. Here are some random pictures. </p>

<div class="mobile-friendly-grid">
  <figure class="grid-card landscape-img">
    <img src="/quadcryo/assets/img/solovaykitaev.jpg" alt="Flash presentation about the project">
    <figcaption>Flash presentation about the project</figcaption>
  </figure>
  
  <figure class="grid-card landscape-img">
    <img src="/quadcryo/assets/img/sabiche.jpg" alt="Sabich">
    <figcaption><a href="https://en.wikipedia.org/wiki/Sabich" target="_blank">Sabich</a>!</figcaption>
  </figure>

  <figure class="grid-card portrait-img">
    <img src="/quadcryo/assets/img/einsteinstatue.jpg" alt="Albert Einstein statue in front of the Ross Building">
    <figcaption>Albert Einstein statue in front of the Ross Building</figcaption>
  </figure>
  
  <figure class="grid-card portrait-img">
    <img src="/quadcryo/assets/img/einsteinpic.jpg" alt="The Einstein Institute of Mathematics at the Hebrew University of Jerusalem (HUJI)">
    <figcaption>The Einstein Institute of Mathematics at the Hebrew University of Jerusalem (HUJI)</figcaption>
  </figure>
</div>

<h5 id="1">(11 June, 2026)</h5>
<p> I suppose now that I have been here for a few more days, I should talk a bit more about the project. I mentioned before that the aim of the REU was to generalize the Solovay-Kitaev theorem to more general groups. The SK Theorem was particularly revolutionary for quantum computing as it established a method for approximating <i> any </i> quantum gate to a very high accuracy and in polylogarithmic time and length. </p>

<p> A paper from Dawson and Nielsen established the main results and provided an algorithmic proof, introducing, loosely, the concept of a <i> balanced group commutator </i> for \(\textrm{SU}(2)\) and \(\textrm{SU}(d)\). It turns out that the existence of the balanced group commutator is a useful tool that comes from compact Lie groups, notably in the inverse mapping from the Lie group to the Lie algebra of \(\textrm{SU}(d)\). Dawson and Nielsen mention an error that is exactly the balanced group commutator, and I learned that it is possible to derive from the <a href="https://en.wikipedia.org/wiki/Baker%E2%80%93Campbell%E2%80%93Hausdorff_formula">BCH formula</a>.  </p>

<p> To think in the minds of people attempting to expand the field of quantum computation, it would seem reasonable to attempt to extend the SK Theorem beyond just compact Lie groups, or perhaps to theoretically suggest an algorithm with a shorter quantum gate sequence and shorter computational time. My mentor suggested a 2002 paper that covered this, and the SK Theorem was improved slightly for specific non-general groups.  </p>

<p> I am still in the early stages of learning the tools, but it turns out that a conceptual approach to generalizing the SK Theorem (but first and foremost, something more theoretical at the intersection of representation theory, Lie theory, and analysis that I cannot grasp quite yet) involves something known as an <a href="https://en.wikipedia.org/wiki/Expander_graphs">expander graph</a>, particularly a <a href="https://en.wikipedia.org/wiki/Cayley_graph">Cayley graph</a>. While I am still sorting out the details of expander graphs, I understand them currently as a graph that has nice connectivity properties—this means that the <a href="https://en.wikipedia.org/wiki/Diameter_(graph_theory)">diameter</a> of the graph is bounded favorably and possesses a value known as the <a href="https://en.wikipedia.org/wiki/Spectral_gap">spectral gap</a>, which measures connectivity—the larger the spectral gap, the more connected a graph is. I've seen \(k\)-regular graphs used largely in this context. Cayley graphs, on the other hand, coming from Cayley's Theorem in group theory, represent group structure in a graph nicely, generating an entire finite group from a generating set; we can denote such graphs as \(\textrm{Cay}(G,S)\) for some group \(G\) and a generating set \(S\). The idea is that the vertices in a Cayley graph represent elements of a quantum gate set, and the edges represent a finite generating set—the choice of this generating set is important, and there are many collections. One that I have seen notably is the Clifford\(+T\) set, containing the \(H\) and \(T\) gates, or the Hadamard and \(\pi/8\) gates respectively. Since Cayley graphs are well connected (this is a non-rigorous way to say it), we might ask how we can formulate a short <a href="https://en.wikipedia.org/wiki/Word_(group_theory)">word</a> from the generating set so as to approximate an arbitrary quantum gate. </p>

<p> Groups in general are discrete objects. This means that there is going to be a feasible word that can be applied to a given quantum gate to reach a target quantum gate. However, in the case of \(\textrm{SU}(2)\), which is also a smooth manifold, such a generating set can be difficult and intensive to obtain.  A 2018 survey paper from Lubotzky and Breuillard that I was instructed to read (and still need to read more of) mentions a new operator, known as a <a href="https://en.wikipedia.org/wiki/Hecke_operator">Hecke operator</a> or "averaging operator" that is needed for a curved space such as \(\textrm{SU}(2)\). I still have to figure out what exactly this operator is in the context of expander graphs, but I'll treat it (and about 80% of the rest of the paper) as a black box for now. One tool, mentioned also in Lubotzky and Breuillard's survey paper, is the idea of golden gates. Golden gates were introduced by Ross and Selinger in a 2014 paper, and, as the name suggests, they are the "golden" approach for generating a group like \(\textrm{SU}(2)\). I still need to read the paper, but surprisingly, there is a decent amount of algebraic number theory at play and I'm excited to see where that goes. I think my mentor has worked closely with golden gates in his recent research. Lots more to read. </p>

<p> Before anything, I think I should mention that I've never read a math research paper at the frontier of math before. Even these papers are a few years old (though constantly re-referenced and cited), but they contain so many ideas that I could not possibly fit into 2 years of undergraduate study, much less 2 months of an REU. I guess I had an idea that math research should be cumulative, as in I should understand all of the vast literature before and have learned every single idea and term mentioned. I think reading through some of these papers, I've learned that I do not understand a million things. And I felt uncomfortable. So many rabbit holes to go down on Wikipedia... and then I see another textbook that I should download. I think ultimately, the main takeaway that I should apply to my work in this REU and future research is the importance of the black box: it shouldn't be used for everything, but "<a href="https://math.stackexchange.com/questions/2016185/is-it-normal-to-treat-math-theorems-as-black-boxes">[n]o new research would ever get done if the researcher tried to intimately understand the entire path from Pythagoras to the state of the art.</a>" I'm an undergraduate, after all. </p>

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/quadcryo/assets/img/einsteinlibrary.jpg" alt="Mathematics library at the Manchester Building">
    <figcaption>Mathematics library at the Manchester Building</figcaption>
  </figure>
</div>

<p> In these few days, I've returned to campus one more time. The REU acquired a computer lab room for work in the future, though it does not have a chalkboard/whiteboard (the temperature may also be controlled and set to frighteningly low temperatures, much to one person's dismay). Above is a picture of the mathematics library—lots and lots of textbooks. If this collection were aggregated and sold online, I can only imagine how valuable it would be—potentially millions, considering 90% of the books appeared to be Springer. </p>

<p> As part of REUs, I think there is a tradition of bringing students to conferences taking place locally. My mentor suggested we attend the <a href="https://iias.huji.ac.il/event/25th-midrasha-mathematicae-groups-expanders-and-codes">Midrasha Mathematicae on Groups, Expanders, and Codes</a> next week, a conference at the Einstein Institute for researchers in the field of quantum computation and the exact area that my REU project is on (without surprise, my mentor is one of the organizers). I expect to understand less than 1% of the material from the talks, but I hope to be able to appreciate the atmosphere and get a taste of what a conference should feel like. Maybe I can ask some good questions if I read more diligently this week!</p>


<h5 id="2">(14 June, 2026)</h5>
<p> I don't expect to update this page as frequently after this as fewer new things will be happening. I attended the first day of the conference, and I must say that doing so was <i> illuminating </i> rather than <i> useful</i>. While I have listened to some small seminars or lectures before, I've never attended a conference that contains a large number of such lectures that contain incredibly dense and cutting-edge mathematics. I went into the conference expecting to understand a very small amount, and even I was surprised. After surveying Breuillard and Lubtozky's paper for some time, I believe I developed a conceptual intution for <i> what was going on</i>, i.e. that the talks (primarily the talks given by Breuillard) were concerned with expander graphs, and that an ultimate goal was to develop notions of expansion and questions of spectral gap in the context of finite simple groups. Most of the details flew over my head, but I enjoyed listening to how various speakers spoke about this research area, and I especially appreciated how I was able to understand some fundamental terms like <a href="https://en.wikipedia.org/wiki/Zariski_topology">Zariski-dense</a>, <a href="https://en.wikipedia.org/wiki/Irreducible_representation">irreducible representation</a>, and more. Below are some photos from the conference. </p>

<div class="triple-image-grid">
  <figure class="grid-card landscape-img">
    <img src="/quadcryo/assets/img/iiasboard1.jpg" alt="Whiteboard notes from Oxford University speaker Emmanuel Breuillard; Uniform expansion for finite simple groups ">
    <figcaption>Whiteboard notes from Oxford University speaker Emmanuel Breuillard ("assuming <a href="https://en.wikipedia.org/wiki/Generalized_Riemann_hypothesis">GRH</a>" on the right); <i> Uniform expansion for finite simple groups </i></figcaption>
  </figure>

  <figure class="grid-card portrait-img">
    <img src="/quadcryo/assets/img/conferenceid.jpg" alt="IIAS conference badge">
    <figcaption>IIAS conference badge</figcaption>
  </figure>

  <figure class="grid-card full-width-row">
    <img src="/quadcryo/assets/img/campuspic.jpg" alt="In the shade outside the IIAS on the Givat Ram campus">
    <figcaption>In the shade outside the IIAS on the Givat Ram campus</figcaption>
  </figure>
</div>

<p> Something that I keep thinking back about is that in research mathematics, people tend to use words like "usually," "almost all," "some," "effective," "sometimes," etc. in reference to results or methods, which just seems so <i> crude</i> from the lack of a better description. I thought mathematics was an indestructible pillar founded on hundreds of year of mathematical formalism—and it is—but it is its crudeness that makes it interesting. I would never have thought mathematics could be similar to applied sciences. But it is. Somehow, trying out different methods and trying to get better and better bounds or isolating particular sets to work in a certain way is akin to watching bacteria multiply or carrying out PCR. </p>

<p> I think this conference was sort of eye-opening for me in a few ways. It excites me that there is so much math on the frontier, but it's a little intimidating. But it was somehow ... relatable that some lecturers said "I don't know" when asked some particularly good questions. There was some shared humor that I didn't understand, but some things were also a bit down to earth, like when the person sitting beside me asked "what are the applications of these results?" I think these aspects of the conference will be among my greatest takeways, mostly because it showcases how mathematics is less of an all-absorbing gel full of pretensious people, and more of a collaborative construction—everyone is putting in their own effort, and developing a vast literature isn't done alone. I hope there is no place for elitism. Perhaps an open question: is it rude to ask something like "how much should I understand?" at a conference like this? </p>

<h5 id = "3">(26 June, 2026)</h5>

<p> About 2 weeks later, we've worked some more on the project. I skimmed some more papers and we've worked on generalizing a result of Dawson-Nielsen to some avail (sort of pictured below), but I think more machinery will be needed if we want to address a more general result. I've started looking a lot more at recent results, and I've sort of fallen down a more conceptual rabbit hole trying to figure out what exactly to look at next. From what I understand, there are two approaches to the topic of SK-like algorithms. Harrow-Recht-Chuang proved a fundamental theoretical result about words of length \(\mathcal{O}(\log(1/\epsilon))\), but their result is a bit too advanced and theoretical to be useful—people want an algorithm nowadays. So what to do? Some later results of Breuillard-Green-Tao (2011) seem to address some fundamental problems and make some good progress in the more discrete case from a conjecture by Lubotzky in the 80s. This references the important result by Helfgott (2008). I was looking for more recent papers on this, and there are a few papers about navigating Cayley graphs that are highly useful. For example Bradford (2021), which so far to me looks the most promising for what we're trying to do. More to read.</p>

  <div class="top-heavy-triple-grid">
  <figure class="grid-card full-width-row">
    <img src="/quadcryo/assets/img/solovaykitaev3.jpg" alt="Solovay-Kitaev theorem extension whiteboard session">
    <figcaption>Pesudo-chalk (whiteboard) presentation about the SK theorem and other stuff</figcaption>
  </figure>

  <figure class="grid-card portrait-img">
    <img src="/quadcryo/assets/img/nationallibrary.jpg" alt="The National Library of Israel building exterior">
    <figcaption>The National Library of Israel</figcaption>
  </figure>

  <figure class="grid-card portrait-img">
    <img src="/quadcryo/assets/img/jewishduck.jpg" alt="Group theory proof notes featuring an Eastern Orthodox duck illustration">
    <figcaption>Eastern Orthodox duck, courtesy of me</figcaption>
  </figure>
</div>

<p> Visited the National Library of Israel. It's a nice library, but I found its exhibition a little underwhelming, maybe because of its lack of things being exhibited. Maybe I'll go back to take a look at some other things. Also, to the right is a duck. I highly recommend ducks, particularly those generated using the <a href = "https://mirrors.ibiblio.org/pub/mirrors/CTAN/graphics/pgf/contrib/tikzducks/tikzducks-doc.pdf">tikzducks package</a>. </p>

<h5 id = "4">(28 June, 2026)</h5>

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/quadcryo/assets/img/reuroom3.jpg" alt="A whiteboard unfortunately">
    <figcaption>A whiteboard unfortunately; for some reason this room is simultaneously on the third and fourth floor</figcaption>
  </figure>
</div>

<h5 id = "5">(3 July, 2026)</h5>

<p> I'm learning quite a few things about research and collaboration. We recently started working on a generalization of the Solovay-Kitaev theorem to <a href = "https://en.wikipedia.org/wiki/P-adic_number">\(p\)-adic integers</a>, denoted \(\mathbb{Z}_{p}\). Stated simply, the generalization objective is the following. Let \(G = SL_{2}(\mathbb{Z}_{p})\), where \(p\) is a prime. Let \(\mathcal{S}\subset G\) be some topologically generated set. Then there exists an algebra for all \(\epsilon>0\) and \(g\in G\) such that there exists an \(l = \mathcal{O}(\log(1/\epsilon)^{4})\) and there are finitely many \(s_{1},s_{2},\ldots,s_{l}\in \mathcal{S}\) such that \(g = s_{1}\cdot s_{2} \cdots s_{l}\). With this construction, it is desirable to work with the corresponding Lie algebra \(\mathfrak{sl}_{2}(\mathbb{Z}_{p})\), as we can copy the method used in the classical SK theorem and ping-pong between the compact Lie group and its corresponding Lie algebra using the exponential and logarithmic maps. As such, a lot of the recent work has been to work on generalizations of certain lemmas that make the classical SK theorem work to \(\mathfrak{sl}_{2}(\mathbb{Z}_{p})\), and as I've been working on recently, \(\mathfrak{sl}_{d}(\mathbb{Z}_{p})\) for some \(d>2\). </p>

<div class="bottom-heavy-triple-grid">
  <figure class="grid-card portrait-img">
    <img src="/quadcryo/assets/img/computerpic1.jpg" alt="Typing up some stuff">
    <figcaption>Typing up some stuff</figcaption>
  </figure>

  <figure class="grid-card portrait-img">
    <img src="/quadcryo/assets/img/hillelst.jpg" alt="Hillel Street">
    <figcaption>Hillel Street</figcaption>
  </figure>

  <figure class="grid-card full-width-row">
    <img src="/quadcryo/assets/img/wbpadics.jpg" alt="p-adics">
    <figcaption>\(p\)-adics and \(\mathfrak{sl}_{d}(\mathbb{Z}_{p})\)</figcaption>
  </figure>
</div>

<p> In working on this, I've had to learn quite a bit more Lie algebra theory. We already managed to solve the \(\mathfrak{sl}_{2}(\mathbb{Z}_{p})\) case, but the \(\mathfrak{sl}_{d}(\mathbb{Z}_{p})\) is a better and more interesting generalization. I have yet to come up with an algorithm, but so far I've learned about the <a href = "https://en.wikipedia.org/wiki/Semisimple_Lie_algebra">root space decomposition</a> (from semisimple Lie algebras), the <a href = "https://en.wikipedia.org/wiki/Cartan_subalgebra">Cartan subalgebra</a>, and a bunch of other terms specific to my usage here. It turns out there are some nice properties that make the \(\mathfrak{sl}_{2}(\mathbb{Z}_{p})\) case more manageable, namely that we can make use of the <a href = "https://en.wikipedia.org/wiki/Chevalley_basis">Chevalley basis</a>. When working in \(\mathfrak{sl}_{d}(\mathbb{Z}_{p})\), however, we have to consider both root spaces and elements of the Cartan subalgebra. This is what I've worked on so far, but of course there are some other directions to take a look at. </p>

<p> The mathematics aside, I've also learned the importance of good references. Bad references are a headache, hypothetically. </p>

<h5 id = "6">(10 July, 2026)</h5>

<p> I'm beginning to get the hang of some aspects of the project, mostly relating to thinking about some problem and digesting new material. It's not uncommon that I will see some terms I haven't seen before, but I believe this is only natural at this point. We allegedly managed to solve the problem in general for \(\mathfrak{sl}_{d}(\mathbb{Z}_{p})\), though I believe there is still significant verification to be done. We were largely considering two different approaches, and some of my contributions partially proved the case in one instance (the Cartan subalgebra) but fell short in root spaces, whereas the other approach could, if treated precisely, be the missing puzzle piece for the problem. This was possible in part due to a completely random 2017 paper by Stasinski covering single commutator representations of elements in \(\mathfrak{sl}_{d}\) defined over any principal ideal ring. </p>

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/quadcryo/assets/img/aushosjlm.jpg" alt="Jerusalem Austrian Hospice view">
    <figcaption>Sunset view of the Jerusalem Old City from the <a href = "https://en.wikipedia.org/wiki/Austrian_Pilgrim_Hospice_to_the_Holy_Family">Austrian Hospice</a></figcaption>
  </figure>
</div>

<p> I suppose at this point, it is meaningful to ask some questions about myself. Considering my position, I think it's reasonable to conclude that I won't be coming up with extremely novel ideas regarding <a href = "https://en.wikipedia.org/wiki/Hasse_principle">local-global principles</a> or anything structural or category-theoretic (which have been suggested). These are complex ideas. So what should I expect to do? I should expect to work hard and come up with small novelties, but I believe I am in no position to create grand results—I think this is a fair position. I've already digested a large amount of new material, and this alone has introduced me to numerous fields and advanced concepts, some even unexpected. For instance, entirely disjoint from the project, I was handed a paper on <a href = "https://en.wikipedia.org/wiki/Supersingular_isogeny_key_exchange">isogeny-based cryptography</a>, which may or may not be interesting to me. The point is, maybe I shouldn't be too hard on myself. After a 4 hour meeting with our mentor several days ago, I left exhausted, having only understood half of what was presented by part of our own group as progress. I think this is natural, and of my own opinion, I think there is a certain point at which I have to stop asking the question "what's going on?" and instead ask "essentially what's going on?". I find this heuristic far more favorable toward me, as, like I mentioned before, it honors the sacred black box of confusion and not-knowing. </p>

<p> This doesn't mean that striving ambitiously for novel results is incorrect. It simply means that the expectation of novelty and competence shouldn't be erroneously founded. </p>

<div class="dual-landscape-grid">
  <figure class="grid-card landscape-img">
    <img src="/quadcryo/assets/img/reu.jpg" alt="Tel Aviv with REU">
    <figcaption>Really rEfined Undergraduates</figcaption>
  </figure>

  <figure class="grid-card landscape-img">
    <img src="/quadcryo/assets/img/solovaykitaev4.jpg" alt="Elementary progress on sl_d(z_p)">
    <figcaption>Elementary computations for \(\mathfrak{sl}_{d}(\mathbb{Z}_{p})\) involving the Cartan subalgebra of its root space decomposition</figcaption>
  </figure>
</div>

<p> Whilst on a train at the ungodly hour of 9:30am, a brief discussion arose concerning the usage of AI in research. I've written about this before <a href = "https://quadcryo.github.io/quadcryo/2026/future-mathematics/">here</a>, but at that point I did not have a vantage from which to think about the impact of AI on research. A question that I genuinely do not know the answer to stems from here: to what degree should one be qualified to assess the novelty and quality of research produced by AI as legitimate contribution to the literature? I think an obvious answer to this question could be "a professional in a given field," though this misses the point. In some mathematics research, the correct line of questioning and tweaking in an LLM should lead to a legitimate mathematical result, seeing as how advanced models are now (though not discounting future potential). This "correct line of questioning" is a lot more vague than it seems though, since theoretically anyone can ask a good or bad question, either leading to novel or non-novel results. So was the "mathematics research conducted" the line of questioning or was it the contents of the responses and the hypothetically novel results? </p>

<p> Parallel to this, since it is well-established that mathematics generated by an LLM is only significant if understandable, is it disingenuous to minimize our own thinking to reserve time for interpreting LLM outputs—and then claim novelty? I'm really not too sure. Is an overdependence on AI in mathematics research just the beginning? </p>

<p> Anyway, off to read a new 2025 paper on a new approach to the Solovay-Kitaev problem. </p>

<h5 id = "7">(12 July, 2026)</h5>

<p> One 2 hour talk later, I acquired some shawarma. This time the topic was a modification of the Solovay-Kitaev algorithm using a new notion known as a <i>higher commutator</i>, introduced by Elkasapy (late) and Thom in a <a href = "https://arxiv.org/abs/1311.0138">2013 paper</a>. There's still more to read in the literature here, but I found some notions in Kuperberg's paper, namely that of so-called "zigzag golf," particularly amusing. </p>

<div class="asymmetric-clearance-grid">
<figure class="grid-card left-diagram">
    <img src="/quadcryo/assets/img/solovaykitaev5.jpg" alt="Presentation notes">
    <figcaption>Zigzag golf in \(\text{SU}(2)\)</figcaption>
  </figure>

  <figure class="grid-card right-cropped-board">
    <img src="/quadcryo/assets/img/greedygolf.png" alt="greedy long distance golf">
    <figcaption>Greedy long distance golf</figcaption>
  </figure>
</div>

<p> The Solovay-Kitaev algorithm cleverly uses single commutators to recursively approximate an arbitrary quantum gate, but the new Solovay-Kitaev type algorithm introduced by Kuperberg uses higher commutators to swing back and forth in a space (like \(\text{SU}(2)\) or \(\text{SU}(d)\)) to gradually approximate an arbitrary quantum gate. The idea is a little complex and has a few conditions, but the idea of the algorithm is very geometric—something that we will have to generalize to something that isn't just a connected compact matrix Lie group. Much more to think about and try to understand. </p>

<p> My mentor also mentioned a funny notion known as "known by the experts." In simple words, it can describe a collection of results that is <i>probably</i> true, but allegedly no one has had the time to write a paper on it. This, allegedly again, is for the students to fill in—a gap in the literature. I find this idea interesting, and perhaps now, maybe even a bit archaic. With AI research becoming commonplace, is mathematical research dense? How many small things like "known by the experts"—things that sound and behave like tradition—will disappear as the filling-of-gaps becomes a menial task for LLMs instead of a tricky problem for a student? Is tradition like this something we should preserve or is it something we should treat as old-fashioned and a look back at older times? </p>

<h5 id = "8">(15 July, 2026)</h5>

<p> I hope some of the entries here, in posterity, both for myself and anyone who bothers to read it, represent how an REU gives a chance to do more stuff than just sit around (or stand around) and think about mathematics all day. In any field, community is vital. People may disagree on many things like philosophy, politics, possibly even the field itself, but the best things about communities like this are the openness of dialogue. </p>

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/quadcryo/assets/img/reusunset.jpg" alt="haifa sunset">
    <figcaption><a href = "https://en.wikipedia.org/wiki/Haifa">https://en.wikipedia.org/wiki/Haifa</a> sunset and a 20km "hike"</figcaption>
  </figure>
</div>

<p> The work is becoming increasingly technical. For instance, whose fault is it that I don't know anything about <a href = "https://en.wikipedia.org/wiki/Lipschitz_continuity">Lipschitz continuity</a>?! Jokes aside, Lie theory is exceptionally beautiful, and I suppose now I'm getting a chance to stroll through it. "We are mathematicians, this is what we do."

<div class="standalone-image-container">
  <figure class="grid-card landscape-img">
    <img src="/quadcryo/assets/img/solovaykitaev6.jpg" alt="kuperberg lie theory">
    <figcaption>Presentation on Lie theory and Kuperberg and Elkasapy's contributions</figcaption>
  </figure>
</div>