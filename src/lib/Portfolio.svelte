<script lang="ts">
  const projects = [
    {
      id: "railinsights",
      title: "Rail Insights",
      subtitle: "",
      tools: "Svelte · MongoDB · Mapbox GL · Python",
      video: "data/railinsights.mp4",
      url: "https://www.rail-insights.co.uk/",
    },
    {
      id: "climatezones",
      title: "Climate Zones",
      subtitle: "",
      tools: "Svelte · D3 · Mapbox · Python",
      video: "data/climate-zones.mov",
      url: "https://pudding.cool/2024/06/climate-zones/",
    },
    {
      id: "ua",
      title: "Urban Access",
      subtitle: "",
      tools: "React · MongoDB · PostgreSQL · Python",
      video: "data/ua1.mov",
      url: "https://www.urbanaccess.io/",
    },
    {
      id: "africa",
      title: "Climate Change in Africa",
      subtitle: "",
      tools: "QGIS · Blender · JavaScript",
      video: "data/af_cli.mp4",
      url: "https://dktaylor916.github.io/climate_africa/",
    },
    {
      id: "tdf",
      title: "Tour de France – Stage 17",
      subtitle: "",
      tools: "QGIS · Mapbox · JavaScript",
      video: "data/tdf.mp4",
      url: "https://dktaylor916.github.io/tdf/",
    },
    {
      id: "sl1",
      title: "Surfline 2022 – A Year in Review",
      subtitle: "",
      tools: "QGIS · Python",
      video: "data/sl-anim.mp4",
      url: "https://vimeo.com/842404323",
    },
    {
      id: "sl2",
      title: "Surfline – How do tides affect our surf?",
      subtitle: "",
      tools: "QGIS · Python · JavaScript · Mapbox",
      video: "data/sl-anim-app.mp4",
      url: "https://dktaylor916.github.io/sl-app/",
    },
    {
      id: "fiets",
      title: "Accessibility of Bike Networks in Amsterdam",
      subtitle: "",
      tools:
        "PostGIS · pgRouting · PostgreSQL · QGIS · JavaScript · D3 · Mapbox",
      video: "data/fietsaccess.mp4",
      url: "https://dktaylor916.github.io/mra_cycle_networks/",
    },
    {
      id: "market",
      title: "A Brief Walk Through the History of Market Street",
      subtitle: "",
      tools: "JavaScript · Mapbox · QGIS",
      video: "data/market1.mp4",
      url: "https://dktaylor916.github.io/marketstreetfinal/",
    },
    {
      id: "ruimte",
      title: "Allocation of Public Space in the Netherlands",
      subtitle: "",
      tools: "JavaScript · D3 · Mapbox · QGIS · PostGIS · PostgreSQL",
      video: "data/ruimte.mp4",
      url: "https://dktaylor916.github.io/nlruimte_v2/",
    },
    {
      id: "liv",
      title: "Liverpool Footfall",
      subtitle: "",
      tools: "QGIS · Python · JavaScript · Mapbox",
      video: "data/liv.mp4",
      url: "https://dktaylor916.github.io/bt_challenge/",
    },
    {
      id: "police",
      title: "Police Violence at US Protests",
      subtitle: "",
      tools: "JavaScript · D3 · Python · QGIS · PostgreSQL · PostGIS",
      video: "data/police1.mp4",
      url: "https://dktaylor916.github.io/US-police-protest-violence/",
    },
    {
      id: "ca",
      title: "How California Slowed Down",
      subtitle: "",
      tools: "Python · QGIS",
      video: "data/ca_vmt.mp4",
      url: "https://dktaylor916.github.io/datavizblog/",
    },
    {
      id: "maps",
      title: "Data Mapping Examples",
      subtitle: "",
      tools: "Python · QGIS · PostgreSQL · PostGIS",
      video: "data/maps.mp4",
      url: "https://dktaylor916.github.io/datamaps/",
    },
  ];

  const skills = [
    {
      title: "GIS",
      items: ["QGIS", "ArcGIS"],
    },
    {
      title: "DB Management",
      items: ["MongoDB", "PostgreSQL", "PostGIS"],
    },
    {
      title: "Python",
      items: ["GeoPandas", "Pandas", "TensorFlow", "Scikit-learn"],
    },
    {
      title: "JavaScript",
      items: ["Svelte", "D3", "React", "Leaflet", "Mapbox"],
    },
    {
      title: "Adobe Suite",
      items: ["InDesign", "Illustrator", "Premiere Pro", "After Effects"],
    },
    {
      title: "Languages",
      items: ["English", "Dutch (B2)", "French (B2)"],
    },
  ];

  const cvPath = "data/ResumeDerekTaylor.pdf";

  function openExternal(url: any) {
    window.open(url, "_blank", "noopener,noreferrer");
  }
  function playVideoFromWrapper(e: MouseEvent) {
    const wrapper = e.currentTarget as HTMLElement;
    const vid = wrapper.querySelector("video") as HTMLVideoElement | null;
    vid?.play();
  }

  function resetVideoFromWrapper(e: MouseEvent) {
    const wrapper = e.currentTarget as HTMLElement;
    const vid = wrapper.querySelector("video") as HTMLVideoElement | null;
    if (vid) {
      vid.pause();
      vid.currentTime = 0;
    }
  }
</script>

<main class="layout">
  <!-- Sidebar -->
  <aside class="sidebar">
    <div class="sidebar-inner">
      <img src="data/picweb.jpg" alt="Derek Taylor" class="avatar" />

      <div class="sidebar-text">
        <h1 class="name">Hi, I'm Derek Taylor.</h1>
        <p class="tagline">
          GIS developer &amp; data viz specialist.<br />
          Discovering the world, one map at a time.
        </p>

        <nav class="nav-links">
          <a href="#portfolio">Portfolio</a>
          <a href="#about">About</a>
          <button class="ghost-button" on:click={() => openExternal(cvPath)}>
            Download CV
          </button>
        </nav>
      </div>
    </div>
  </aside>

  <!-- Main content -->
  <section class="main">
    <!-- Portfolio -->
    <section id="portfolio" class="section">
      <h2 class="section-title">Selected Work</h2>

      <div class="projects">
        {#each projects as project}
          <article
            class="project-card"
            on:click={() => openExternal(project.url)}
            tabindex="0"
          >
            <div
              class="video-wrapper"
              on:mouseenter={playVideoFromWrapper}
              on:mouseleave={resetVideoFromWrapper}
            >
              <video
                src={project.video}
                muted
                loop
                playsinline
                preload="metadata"
              ></video>

              <div class="overlay">
                <div class="overlay-text">
                  <h3>{project.title}</h3>
                  {#if project.subtitle}
                    <p class="subtitle">{project.subtitle}</p>
                  {/if}
                  <p class="tools"><span>Tools:</span> {project.tools}</p>
                </div>
              </div>
            </div>
          </article>
        {/each}
      </div>
    </section>

    <!-- About -->
    <section id="about" class="section about">
      <h2 class="section-title">About Me</h2>

      <div class="about-grid">
        <div class="about-text">
          <p>
            I’m a full-stack GIS developer and data visualization specialist
            with over eight years of professional experience. I focus on
            transforming complex data into clear, actionable insights and
            communicating results to both technical and non-technical audiences.
          </p>
          <p>
            My work spans cleaning and maintaining large datasets, building
            backend data pipelines and APIs, and developing compelling frontend
            interactive visualizations.
          </p>
          <p>
            When I’m not making maps for work, I’m making maps for side
            projects, conducting open-source investigations, and exploring the
            world through numbers and visualizations. I’ve used big datasets to
            uncover stories and provide clear and concise information to
            municipalities, stakeholders, and non-profits. I’m especially
            interested in the
            <strong>intersection of data and journalism</strong>, using dynamic,
            interactive visualizations to bring static spreadsheets and text to
            life.
          </p>
          <p>
            After I close the computer for the day, you can find me biking into
            headwinds, playing drums, and jumping into cold bodies of water.
          </p>

          <div class="contact">
            <p>
              <strong>Mail:</strong>
              <a href="mailto:dktaylor916@gmail.com">dktaylor916@gmail.com</a>
            </p>
            <p><strong>Tel:</strong> +44 (0)7724 113 738</p>
          </div>

          <button class="primary-button" on:click={() => openExternal(cvPath)}>
            Download CV
          </button>
        </div>

        <div class="skills-panel">
          <h3>Technical Skills</h3>
          <div class="skills-grid">
            {#each skills as group}
              <div class="skill-group">
                <h4>{group.title}</h4>
                <ul>
                  {#each group.items as item}
                    <li>{item}</li>
                  {/each}
                </ul>
              </div>
            {/each}
          </div>
        </div>
      </div>
    </section>
  </section>
</main>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Staatliches&display=swap");

  :global(body) {
    margin: 0;
    font-family:
      "Montserrat",
      system-ui,
      -apple-system,
      BlinkMacSystemFont,
      "Segoe UI",
      sans-serif;
    background: #fffaf0;
    color: #1d1d1f;
  }

  .layout {
    display: flex;
    min-height: 100vh;
  }

  .sidebar {
    width: 360px;
    background: linear-gradient(180deg, #5e8793, #4e707a);
    color: #fff;
    padding: 2.5rem 2rem;
    position: sticky;
    top: 0;
    align-self: flex-start;
    min-height: 100vh;
    box-shadow: 0 0 40px rgba(0, 0, 0, 0.18);
    z-index: 10;
  }

  .sidebar-inner {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1.75rem;
  }

  .avatar {
    width: 62%;
    max-width: 220px;
    border-radius: 50%;
    border: 3px solid rgba(255, 255, 255, 0.65);
    box-shadow: 0 16px 40px rgba(0, 0, 0, 0.4);
    object-fit: cover;
  }

  .sidebar-text {
    text-align: center;
  }

  .name {
    font-family: "Staatliches", system-ui;
    font-size: 2.4rem;
    letter-spacing: 0.04em;
    margin: 0 0 0.5rem;
  }

  .tagline {
    margin: 0 0 1.5rem;
    font-size: 0.96rem;
    line-height: 1.5;
    opacity: 0.9;
  }

  .nav-links {
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
    align-items: stretch;
  }

  .nav-links a,
  .ghost-button {
    font-family: "Staatliches", system-ui;
    letter-spacing: 0.11em;
    text-transform: uppercase;
    font-size: 0.82rem;
    border-radius: 999px;
    padding: 0.65rem 1.2rem;
    border: 1px solid rgba(255, 255, 255, 0.45);
    background: rgba(255, 255, 255, 0.06);
    color: #fff;
    text-decoration: none;
    text-align: center;
    cursor: pointer;
    transition:
      background 150ms ease,
      transform 150ms ease,
      box-shadow 150ms ease,
      border-color 150ms ease;
  }

  .nav-links a:hover,
  .ghost-button:hover {
    background: rgba(255, 255, 255, 0.18);
    border-color: rgba(255, 255, 255, 0.9);
    box-shadow: 0 10px 24px rgba(0, 0, 0, 0.35);
    transform: translateY(-1px);
  }

  .main {
    flex: 1;
    padding: 2.5rem 3.5rem;
    max-width: 1100px;
    margin: 0 auto;
  }

  .section {
    margin-bottom: 4rem;
  }

  .section-title {
    font-family: "Staatliches", system-ui;
    font-size: 2.5rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin: 0 0 1.5rem;
    color: #2b3138;
    position: relative;
  }

  .section-title::after {
    content: "";
    position: absolute;
    left: 0;
    bottom: -0.4rem;
    width: 76px;
    height: 3px;
    border-radius: 999px;
    background: linear-gradient(90deg, #da4167, transparent);
  }

  .projects {
    display: flex;
    flex-direction: column;
    gap: 2.25rem;
  }

  .project-card {
    cursor: pointer;
    border-radius: 1.25rem;
    overflow: hidden;
    background: rgba(255, 255, 255, 0.9);
    box-shadow: 0 18px 45px rgba(0, 0, 0, 0.12);
    transition:
      transform 180ms ease,
      box-shadow 180ms ease;
  }

  .project-card:focus-visible {
    outline: 2px solid #da4167;
    outline-offset: 3px;
  }

  .project-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 24px 65px rgba(0, 0, 0, 0.18);
  }

  .video-wrapper {
    position: relative;
    overflow: hidden;
  }

  .video-wrapper video {
    width: 100%;
    height: 100%;
    display: block;
    object-fit: cover;
    transform: scale(1);
    transition: transform 200ms ease;
  }

  .project-card:hover .video-wrapper video {
    transform: scale(1);
  }

  .overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(
      180deg,
      rgba(0, 0, 0, 0.1) 15%,
      rgba(0, 0, 0, 0.65) 80%,
      rgba(0, 0, 0, 0.85) 100%
    );
    display: flex;
    justify-content: flex-end;
    align-items: flex-end;
    padding: 1.4rem 1.7rem;
    color: #fff;
    opacity: 0;
    transform: translateY(10px);
    transition:
      opacity 200ms ease,
      transform 200ms ease;
  }

  .project-card:hover .overlay {
    opacity: 1;
    transform: translateY(0);
  }

  .overlay-text h3 {
    margin: 0 0 0.2rem;
    font-family: "Staatliches", system-ui;
    font-size: clamp(1.4rem, 2vw, 1.8rem);
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .subtitle {
    margin: 0 0 0.4rem;
    font-size: 0.9rem;
    opacity: 0.9;
  }

  .tools {
    margin: 0;
    font-size: 0.9rem;
    opacity: 0.95;
  }

  .tools span {
    font-weight: 600;
  }

  .about {
    margin-bottom: 5rem;
  }

  .about-grid {
    display: grid;
    grid-template-columns: minmax(0, 3fr) minmax(0, 2.5fr);
    gap: 2.5rem;
    align-items: flex-start;
  }

  .about-text p {
    margin: 0 0 1rem;
    line-height: 1.65;
    font-size: 0.98rem;
  }

  .contact {
    margin: 1.5rem 0 1.5rem;
    font-size: 0.95rem;
  }

  .contact a {
    color: inherit;
    text-decoration: none;
    border-bottom: 1px solid rgba(0, 0, 0, 0.2);
  }

  .contact a:hover {
    border-bottom-color: #da4167;
  }

  .primary-button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 0.75rem 1.6rem;
    border-radius: 999px;
    border: none;
    cursor: pointer;
    font-family: "Staatliches", system-ui;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    font-size: 0.85rem;
    background: #da4167;
    color: #fff;
    transition:
      transform 150ms ease,
      box-shadow 150ms ease,
      background 150ms ease;
  }

  .primary-button:hover {
    transform: translateY(-1px);
    background: #c23358;
  }

  .skills-panel {
    background: rgba(255, 255, 255, 0.9);
    border-radius: 1.5rem;
    padding: 1.6rem 1.8rem;
    box-shadow: 0 16px 40px rgba(0, 0, 0, 0.08);
    backdrop-filter: blur(12px);
  }

  .skills-panel h3 {
    margin: 0 0 1rem;
    font-family: "Staatliches", system-ui;
    font-size: 1.3rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 1rem 1.2rem;
  }

  .skill-group h4 {
    margin: 0 0 0.35rem;
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    font-weight: 600;
    color: #555;
  }

  .skill-group ul {
    list-style: none;
    padding: 0;
    margin: 0;
    font-size: 0.88rem;
    line-height: 1.5;
  }

  .skill-group li::before {
    content: "• ";
    color: #da4167;
  }

  /* Responsive */

  @media (max-width: 960px) {
    .layout {
      flex-direction: column;
    }

    .sidebar {
      position: static;
      width: 97%;
      min-height: auto;
      padding: 1.3rem 1.5rem;
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.2);
    }

    .sidebar-inner {
      flex-direction: row;
      align-items: center;
      justify-content: space-between;
      gap: 1.25rem;
    }

    .sidebar-text {
      text-align: left;
    }

    .avatar {
      width: 26vw;
      max-width: 140px;
    }

    .name {
      font-size: 1.7rem;
    }

    .tagline {
      font-size: 0.85rem;
    }

    .nav-links {
      flex-direction: row;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-top: 0.4rem;
    }

    .main {
      padding: 1.8rem 1.4rem 3rem;
    }

    .section-title {
      font-size: 2rem;
    }

    .about-grid {
      grid-template-columns: minmax(0, 1fr);
    }
  }

  @media (max-width: 600px) {
    .overlay {
      opacity: 1;
      background: linear-gradient(
        180deg,
        rgba(0, 0, 0, 0.1) 10%,
        rgba(0, 0, 0, 0.85) 90%
      );
    }

    .project-card:hover .overlay {
      transform: translateY(0);
    }

    .section-title::after {
      width: 60px;
    }
  }
</style>
