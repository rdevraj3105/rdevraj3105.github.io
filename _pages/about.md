---
layout: about
title: about
permalink: /
subtitle:

profile:
  align: right
  image: 
  address: >

news: false
social: true
selected_papers: true
---

<!-- Style for seamless dark mode transitions -->
<style>
  body {
    background: var(--global-bg-color);
    color: var(--global-text-color);
    transition: background 0.4s cubic-bezier(.4,0,.2,1), color 0.4s cubic-bezier(.4,0,.2,1);
  }
  .content-container {
    width: 50vw;
    min-width: 320px;
    max-width: 650px;
    margin-right: 2vw;
    position: relative;
    z-index: 1;
    background: transparent; /* transparent for seamless transition */
    color: var(--global-text-color);
    padding: 2rem 2rem 2rem 0;
    box-sizing: border-box;
    transition: background 0.4s cubic-bezier(.4,0,.2,1), color 0.4s cubic-bezier(.4,0,.2,1);
  }
  @media (max-width: 900px) {
    .content-container {
      width: 100vw;
      margin-right: 0;
      padding: 1rem 0.5rem;
    }
    #neural-net {
      display: none;
    }
  }
  #neural-net {
    pointer-events: none;
    background: transparent !important;
    transition: background 0.4s cubic-bezier(.4,0,.2,1);
  }
</style>

<div class="content-container">
I am a rising 3rd-year undergraduate at the <a href="http://gatech.edu">Georgia Institute of Technology</a> pursuing a B.S. in <a href="https://www.isye.gatech.edu/">Industrial &amp; Systems Engineering</a>, specializing in <a href="https://www.isye.gatech.edu/academics/undergraduate/degrees/operations-research">Operations Research</a> with a minor in <a href="https://www.cc.gatech.edu/">Computer Science</a> (concentration in artificial intelligence/machine learning). I am passionate about optimization and data science.

<br><br>

I am also involved in undergraduate research with the <a href="https://ssog.ae.gatech.edu/">Space Systems Optimization Group</a>, where I am advised by <a href="https://ae.gatech.edu/directory/person/koki-ho">Prof. Koki Ho</a>.

<br><br>

In addition to my academic and research work, I serve as an associate for the <a href="https://gtangelnetwork.com">GT Angel Network</a>, helping lead Georgia Tech’s first angel investment network.
</div>

<!-- Particles container for right-side neural net effect -->
<div id="neural-net" style="position: fixed; top: 0; right: 0; width: 40vw; height: 60vh; z-index: -1; pointer-events: none; background: transparent;"></div>

<!-- tsParticles via CDN and theme-aware support -->
<script src="https://cdn.jsdelivr.net/npm/tsparticles@1.37.0/tsparticles.min.js"></script>
<script>
  // Helper to read a CSS variable from :root
  function getCssVar(name) {
    return getComputedStyle(document.documentElement).getPropertyValue(name).trim();
  }

  function getParticleColors() {
    return {
      particleColor: getCssVar('--global-theme-color') || "#FCC",
      linkColor: getCssVar('--global-theme-color') || "#999"
    };
  }

  // Initial load
  tsParticles.load("neural-net", {
    fullScreen: { enable: false },
    background: { color: "transparent" }, // transparent for seamless transition
    particles: {
      number: {
        value: 85,
        density: { enable: true, value_area: 600 }
      },
      color: { value: getCssVar('--global-theme-color') || "#FCC" },
      shape: { type: "circle" },
      opacity: { value: 0.2 },
      size: { value: 6 },
      links: {
        enable: true,
        distance: 250,
        color: getCssVar('--global-theme-color') || "#999",
        opacity: 0.25,
        width: 1
      },
      move: {
        enable: true,
        speed: 0.8,
        direction: "none",
        straight: false,
        outModes: { default: "bounce" },
        attract: { enable: false }
      },
      rotate: {
        value: { min: 0, max: 360 },
        direction: "random",
        animation: {
          enable: true,
          speed: 10,
          sync: false
        }
      }
    },
    interactivity: {
      events: {
        onhover: { enable: true, mode: "grab" },
        onclick: { enable: true, mode: "push" },
        resize: true
      },
      modes: {
        grab: { distance: 140, line_linked: { opacity: 0.2 } },
        push: { particles_nb: 4 }
      }
    },
    retina_detect: true
  }).then((container) => {
    // Listen for theme changes and update particle/link colors
    const observer = new MutationObserver(() => {
      const {particleColor, linkColor} = getParticleColors();
      container.options.particles.color.value = particleColor;
      container.options.particles.links.color = linkColor;
      container.refresh();
    });
    observer.observe(document.documentElement, { attributes: true, attributeFilter: ['data-theme'] });

    // Optional: re-sync on page show (bfcache)
    window.addEventListener('pageshow', () => {
      const {particleColor, linkColor} = getParticleColors();
      container.options.particles.color.value = particleColor;
      container.options.particles.links.color = linkColor;
      container.refresh();
    });
  });
</script>
