<script lang="ts">
  const projects = [
    {
      id: "railinsights",
      title: "Rail Insights",
      subtitle: "",
      tools: "Svelte · MongoDB · Mapbox GL · Python",
      video: "data/railinsights.mp4",
      url: "https://www.rail-insights.co.uk/",
      role: "Lead Developer",
      goal: "Provide Network Rail UK with an interactive dashboard to visualise outputs from their transport model",
      outcome:
        "Designed and built out both front and backend. Streamlined Network Rail's data communication for both external and internal use to help improve services",
    },
    {
      id: "climatezones",
      title: "Climate Zones",
      subtitle: "",
      tools: "Svelte · D3 · Mapbox · Python",
      video: "data/climate-zones.mov",
      url: "https://pudding.cool/2024/06/climate-zones/",
      role: "Lead Author / Developer",
      goal: "Help non-technical readers understand how their city’s climate could shift under different emissions scenarios.",
      outcome:
        "Published as an interactive feature on The Pudding, an award-winning online data visualization publication.",
    },
    {
      id: "ua",
      title: "Urban Access",
      subtitle:
        "A web platform that lets planners instantly measure public transport accessibility, population density, and local amenities for 15-minute cities.",
      tools: "React · MongoDB · PostgreSQL · Python",
      video: "data/ua1.mov",
      url: "https://www.urbanaccess.io/",
      role: "Lead Developer",
      goal: "Build a self-serve accessibility analysis tool so municipalities and consultants can assess transport accessibility, population catchments, and amenity access without bespoke GIS workflows.",
      outcome:
        "Launched as a commercial web app with instant analysis, downloadable GTFS data, and shareable accessibility reports for urban planning teams.",
    },

    {
      id: "africa",
      title: "Climate Change in Africa",
      subtitle:
        "A scroll-driven story showing how warming reshapes Africa’s climate zones and shrinks familiar climate bands.",
      tools: "QGIS · Blender · JavaScript",
      video: "data/af_cli.mp4",
      url: "https://dktaylor916.github.io/climate_africa/",
      role: "Lead Developer",
      goal: "Visualise projected shifts in African climate zones using clear maps and animation for a general, non-technical audience.",
      outcome:
        "Published as a standalone explainer combining 3D renders and interactive maps to communicate regional climate risks.",
    },
    {
      id: "tdf",
      title: "Tour de France – Stage 17",
      subtitle:
        "An interactive map and elevation profile exploring one of the Tour de France’s key high-mountain stages.",
      tools: "QGIS · Mapbox · JavaScript",
      video: "data/tdf.mp4",
      url: "https://dktaylor916.github.io/tdf/",
      role: "Lead Developer",
      goal: "Experiment with race storytelling by mapping gradients, distance, and key segments along Stage 17 of the Tour.",
      outcome:
        "Created an explorable stage overview that links geography, elevation, and race context in a single interactive view.",
    },
    {
      id: "sl1",
      title: "Surfline 2022 – A Year in Review",
      subtitle:
        "An animated overview of global swell, storms, and standout events from Surfline’s 2022 surf year.",
      tools: "QGIS · Python",
      video: "data/sl-anim.mp4",
      url: "https://vimeo.com/842404323",
      role: "Lead Developer",
      goal: "Process and visualise a year of ocean and wave data to tell a coherent, visually engaging story for surfers.",
      outcome:
        "Delivered a motion-graphics piece used by Surfline to summarise and highlight the most memorable waves of 2022.",
    },
    {
      id: "sl2",
      title: "Surfline – How do tides affect our surf?",
      subtitle:
        "An interactive explainer that shows how changing tides affect wave quality across different surf breaks.",
      tools: "QGIS · Python · JavaScript · Mapbox",
      video: "data/sl-anim-app.mp4",
      url: "https://dktaylor916.github.io/sl-app/",
      role: "Lead Developer",
      goal: "Help surfers understand how tide windows shape surf conditions at their local spots using real data and intuitive visuals.",
      outcome:
        "Shipped as a browser-based tool that combines explorable maps and charts to link tides, bathymetry, and wave quality.",
    },
    {
      id: "fiets",
      title: "Accessibility of Bike Networks in Amsterdam",
      subtitle:
        "A scenario tool comparing how different bike network investments change access to jobs across the Amsterdam metropolitan region.",
      tools:
        "PostGIS · pgRouting · PostgreSQL · QGIS · JavaScript · D3 · Mapbox",
      video: "data/fietsaccess.mp4",
      url: "https://dktaylor916.github.io/mra_cycle_networks/",
      role: "Lead Developer",
      goal: "Support planners in testing reference, upgraded, and speed-pedelec bike network scenarios using 45-minute job accessibility as a metric.",
      outcome:
        "Built an interactive map where each origin shows how far you can travel and how many jobs you can reach under each network scenario.",
    },
    {
      id: "market",
      title: "A Brief Walk Through the History of Market Street",
      subtitle:
        "A story map tracing how San Francisco’s Market Street has evolved through changing transport, planning, and public space decisions.",
      tools: "JavaScript · Mapbox · QGIS",
      video: "data/market1.mp4",
      url: "https://dktaylor916.github.io/marketstreetfinal/",
      role: "Lead Developer",
      goal: "Combine archival material and modern geospatial data to show how Market Street’s form and function have shifted over time.",
      outcome:
        "Produced a scroll-based narrative with maps and context that lets readers visually compare historic and contemporary Market Street.",
    },
    {
      id: "ruimte",
      title: "Allocation of Public Space in the Netherlands",
      subtitle:
        "Interactive maps showing how public space is divided between cars, parking, cyclists, and pedestrians at neighbourhood, district, and city levels.",
      tools: "JavaScript · D3 · Mapbox · QGIS · PostGIS · PostgreSQL",
      video: "data/ruimte.mp4",
      url: "https://dktaylor916.github.io/nlruimte_v2/",
      role: "Lead Developer",
      goal: "Quantify who public space is really for in the Netherlands by classifying a national dataset and aggregating it by user and geography.",
      outcome:
        "Built a multi-scale dashboard that makes it easy to compare the share of space allocated to different modes across cities and neighbourhoods.",
    },
    {
      id: "liv",
      title: "Liverpool Footfall",
      subtitle:
        "An exploratory dashboard mapping how pedestrian activity varies across Liverpool’s streets over time.",
      tools: "QGIS · Python · JavaScript · Mapbox",
      video: "data/liv.mp4",
      url: "https://dktaylor916.github.io/bt_challenge/",
      role: "Lead Developer",
      goal: "Use telecom-derived footfall or sensor data to show when and where people use Liverpool’s city centre, with an emphasis on the high street.",
      outcome:
        "Delivered an interactive prototype that allows users to explore spatial and temporal patterns in city-centre footfall.",
    },
    {
      id: "police",
      title: "Police Violence at US Protests",
      subtitle:
        "A data-driven map and chart interface showing reported incidents of police violence at protests across the United States.",
      tools: "JavaScript · D3 · Python · QGIS · PostgreSQL · PostGIS",
      video: "data/police1.mp4",
      url: "https://dktaylor916.github.io/US-police-protest-violence/",
      role: "Lead Developer",
      goal: "Integrate protest-event and police use-of-force datasets to reveal where, when, and against whom violence occurred.",
      outcome:
        "Produced an explorable interface that lets users filter incidents by city, tactic, and outcome to better understand national patterns.",
    },
    {
      id: "ca",
      title: "How California Slowed Down",
      subtitle:
        "A long-form analysis of how vehicle miles traveled changed across California, particularly during the COVID-19 pandemic.",
      tools: "Python · QGIS",
      video: "data/ca_vmt.mp4",
      url: "https://dktaylor916.github.io/datavizblog/",
      role: "Lead Developer",
      goal: "Analyse mobility and traffic datasets to quantify how much, where, and for how long driving activity declined.",
      outcome:
        "Published as a web essay combining charts and maps to highlight regional differences in travel behaviour and recovery.",
    },
    {
      id: "maps",
      title: "Data Mapping Examples",
      subtitle:
        "A curated collection of thematic maps and spatial analyses built from open datasets and custom geoprocessing.",
      tools: "Python · QGIS · PostgreSQL · PostGIS",
      video: "data/maps.mp4",
      url: "https://dktaylor916.github.io/datamaps/",
      role: "Lead Developer",
      goal: "Experiment with geospatial pipelines and cartographic styles using Python, PostGIS, and QGIS across a variety of datasets.",
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
      <p>
        The following examples are a blend of professional and personal
        projects, covering frontend UI/UX, data analysis/management, and visual
        storytelling.
      </p>
      <p></p>
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

                  <p class="tools"><span>Goal:</span> {project.goal}</p>
                  <p class="tools"><span>Outcome:</span> {project.outcome}</p>
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
    background: #f5f5f7;
    color: #111827;
  }

  .layout {
    display: flex;
    min-height: 100vh;
  }

  .sidebar {
    width: 340px;
    background: #243766; /* deep slate */
    color: #f9fafb;
    padding: 2.5rem 2rem;
    position: sticky;
    top: 0;
    align-self: flex-start;
    min-height: 100vh;
    border-right: 1px solid #1f2937;
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
    border: 2px solid rgba(148, 163, 184, 0.9);
    object-fit: cover;
  }

  .sidebar-text {
    text-align: center;
  }

  .name {
    /* font-family: "Staatliches", system-ui; */
    font-size: 2em;
    /* letter-spacing: 0.1em; */
    margin: 0 0 0.6rem;
  }

  .tagline {
    margin: 0 0 1.5rem;
    font-size: 0.9rem;
    line-height: 1.6;
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
    letter-spacing: 0.16em;
    text-transform: uppercase;
    font-size: 1rem;
    border-radius: 999px;
    padding: 0.6rem 1.2rem;
    border: 1px solid rgba(249, 250, 251, 0.25);
    background: transparent;
    color: #f9fafb;
    text-decoration: none;
    text-align: center;
    cursor: pointer;
    transition:
      background 150ms ease,
      transform 150ms ease,
      border-color 150ms ease,
      color 150ms ease;
  }

  .nav-links a:hover,
  .ghost-button:hover {
    background: rgba(249, 250, 251, 0.08);
    border-color: rgba(249, 250, 251, 0.6);
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
    font-size: 2.4rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    margin: 0 0 1.5rem;
    color: #111827;
    position: relative;
  }

  .section-title::after {
    content: "";
    position: absolute;
    left: 0;
    bottom: -0.4rem;
    width: 88px;
    height: 2px;
    border-radius: 999px;
    background: linear-gradient(90deg, #243766, transparent);
  }

  .projects {
    display: flex;
    flex-direction: column;
    gap: 1.9rem;
  }

  .project-card {
    cursor: pointer;
    border-radius: 1.25rem;
    overflow: hidden;
    background: #ffffff;
    border: 1px solid #e5e7eb;
    transition:
      transform 180ms ease,
      border-color 180ms ease,
      background 180ms ease;
  }

  .project-card:focus-visible {
    outline: 2px solid #243766;
    outline-offset: 3px;
  }

  .project-card:hover {
    transform: translateY(-2px);
    border-color: #243766;
    background: #f9fafb;
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
    transition: transform 220ms ease;
  }

  .project-card:hover .video-wrapper video {
    transform: scale(1.02);
  }

  .overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(
      180deg,
      rgba(15, 23, 42, 0.05) 10%,
      rgba(15, 23, 42, 0.8) 90%
    );
    display: flex;

    align-items: flex-end;
    padding: 1.4rem 1.7rem;
    color: #f9fafb;
    opacity: 0;
    transform: translateY(8px);
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
    font-size: 36px;
    letter-spacing: 0.16em;
    text-transform: uppercase;
  }
  .overlay-text {
    position: relative;
  }

  .subtitle {
    margin: 0 0 0.4rem;
    font-size: 0.9rem;
    opacity: 0.9;
  }

  .tools {
    margin: 0;
    font-size: 14px;
    opacity: 0.95;
  }

  .tools span {
    font-weight: 600;
    font-size: 16px;
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
    line-height: 1.7;
    font-size: 0.98rem;
    color: #111827;
  }

  .contact {
    margin: 1.6rem 0 1.6rem;
    font-size: 0.95rem;
  }

  .contact a {
    color: #243766;
    text-decoration: none;
    border-bottom: 1px solid rgba(37, 99, 235, 0.25);
  }

  .contact a:hover {
    border-bottom-color: #243766;
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
    letter-spacing: 0.18em;
    font-size: 0.82rem;
    background: #243766;
    color: #f9fafb;
    transition:
      transform 150ms ease,
      background 150ms ease;
  }

  .primary-button:hover {
    transform: translateY(-1px);
    background: #1d4ed8;
  }

  .skills-panel {
    background: #ffffff;
    border-radius: 1.25rem;
    padding: 1.6rem 1.8rem;
    border: 1px solid #e5e7eb;
  }

  .skills-panel h3 {
    margin: 0 0 1rem;
    font-family: "Staatliches", system-ui;
    font-size: 1.2rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #111827;
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 1rem 1.2rem;
  }

  .skill-group h4 {
    margin: 0 0 0.35rem;
    font-size: 0.85rem;
    text-transform: uppercase;
    letter-spacing: 0.16em;
    font-weight: 600;
    color: #6b7280;
  }

  .skill-group ul {
    list-style: none;
    padding: 0;
    margin: 0;
    font-size: 0.88rem;
    line-height: 1.5;
    color: #111827;
  }

  .skill-group li::before {
    content: "• ";
    color: #243766;
  }

  /* Responsive */

  @media (max-width: 960px) {
    .layout {
      flex-direction: column;
    }

    .sidebar {
      position: static;
      width: 100%;
      min-height: auto;
      padding: 1.4rem 1.5rem;
      border-right: none;
      border-bottom: 1px solid #1f2937;
    }

    .sidebar-inner {
      flex-direction: row;
      align-items: center;
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
        rgba(15, 23, 42, 0.05) 10%,
        rgba(15, 23, 42, 0.9) 90%
      );
    }

    .project-card:hover .overlay {
      transform: translateY(0);
    }

    .section-title::after {
      width: 64px;
    }
  }
</style>
