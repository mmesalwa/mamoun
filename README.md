<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Entretien Audencia — Mamoun Alami</title>
<style>
  :root {
    --bg: #0f172a;
    --card: #1e293b;
    --card-hover: #334155;
    --card-active: #2563eb;
    --text: #f8fafc;
    --muted: #94a3b8;
    --border: #334155;
    --accent: #38bdf8;
    --en-accent: #10b981;
    --en-active: #059669;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    background: var(--bg);
    color: var(--text);
    padding: 16px;
    line-height: 1.55;
  }
  .container { max-width: 1400px; margin: 0 auto; }
  header {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    padding-bottom: 14px;
    margin-bottom: 18px;
    border-bottom: 1px solid var(--border);
  }
  header h1 { font-size: 1.35rem; font-weight: 700; color: #fff; }
  header p { font-size: 0.85rem; color: var(--muted); }
  .tabs { display: flex; gap: 8px; }
  .tab-btn {
    background: var(--card);
    color: var(--text);
    border: 1px solid var(--border);
    padding: 8px 14px;
    border-radius: 8px;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: 0.15s;
  }
  .tab-btn.active { background: var(--card-active); border-color: var(--accent); color: #fff; }

  .section { margin-bottom: 28px; }
  .section-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 12px;
  }
  .section-title {
    font-size: 1.1rem;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .badge {
    font-size: 0.75rem;
    padding: 2px 8px;
    border-radius: 999px;
    background: rgba(56, 189, 248, 0.15);
    color: var(--accent);
    font-weight: 600;
  }
  .badge.en {
    background: rgba(16, 185, 129, 0.15);
    color: var(--en-accent);
  }

  /* Panneau de réponse */
  .answer-box {
    display: none;
    background: #172033;
    border: 2px solid var(--accent);
    border-radius: 12px;
    padding: 18px 20px;
    margin-bottom: 14px;
    box-shadow: 0 10px 25px rgba(0,0,0,0.4);
  }
  .answer-box.en { border-color: var(--en-accent); }
  .answer-box.visible { display: block; }
  .answer-top {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 12px;
    margin-bottom: 12px;
    padding-bottom: 10px;
    border-bottom: 1px solid var(--border);
  }
  .answer-q {
    font-size: 1.05rem;
    font-weight: 700;
    color: var(--accent);
  }
  .answer-box.en .answer-q { color: var(--en-accent); }
  .answer-controls { display: flex; gap: 6px; flex-shrink: 0; }
  .ctrl-btn {
    background: var(--card);
    color: var(--text);
    border: 1px solid var(--border);
    padding: 6px 10px;
    border-radius: 6px;
    font-size: 0.8rem;
    font-weight: 600;
    cursor: pointer;
  }
  .ctrl-btn:hover { background: var(--card-hover); }
  .ctrl-btn.close { background: #7f1d1d; border-color: #991b1b; }
  .answer-body {
    font-size: 1.05rem;
    line-height: 1.65;
    color: #f1f5f9;
    white-space: pre-line;
  }

  /* Grille 5 blocs par ligne sur écran large, adaptative sur mobile/tablette */
  .grid-5 {
    display: grid;
    grid-template-columns: repeat(5, minmax(0, 1fr));
    gap: 8px;
  }
  @media (max-width: 1100px) {
    .grid-5 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
  }
  @media (max-width: 680px) {
    .grid-5 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  }

  .q-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 11px;
    text-align: left;
    color: var(--text);
    cursor: pointer;
    transition: transform 0.1s, background 0.15s, border-color 0.15s;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    gap: 4px;
    min-height: 76px;
  }
  .q-card:hover {
    background: var(--card-hover);
    border-color: var(--accent);
    transform: translateY(-1px);
  }
  .q-card.active {
    background: var(--card-active);
    border-color: #93c5fd;
  }
  .q-card.en:hover { border-color: var(--en-accent); }
  .q-card.en.active {
    background: var(--en-active);
    border-color: #6ee7b7;
  }
  .q-num {
    font-size: 0.72rem;
    font-weight: 800;
    color: var(--accent);
    text-transform: uppercase;
    letter-spacing: 0.03em;
  }
  .q-card.en .q-num { color: var(--en-accent); }
  .q-card.active .q-num { color: #fff; }
  .q-text {
    font-size: 0.82rem;
    font-weight: 600;
    line-height: 1.3;
    color: #f8fafc;
  }
</style>
</head>
<body>
<div class="container">
  <header>
    <div>
      <h1>Entretien Bachelor Audencia — Mamoun Alami</h1>
      <p>Clique sur une question pour afficher ta réponse exacte (compatible téléphone, tablette, PC & Mac)</p>
    </div>
    <div class="tabs">
      <button class="tab-btn active" onclick="filterView('all', this)">Tout afficher</button>
      <button class="tab-btn" onclick="filterView('fr', this)">Français (8)</button>
      <button class="tab-btn" onclick="filterView('en', this)">English (15)</button>
    </div>
  </header>

  <!-- BLOC FRANÇAIS -->
  <section class="section" id="sec-fr">
    <div class="section-header">
      <div class="section-title">🇫🇷 Entretien en Français <span class="badge">8 questions</span></div>
    </div>

    <div class="answer-box" id="box-fr">
      <div class="answer-top">
        <div class="answer-q" id="q-fr"></div>
        <div class="answer-controls">
          <button class="ctrl-btn" onclick="step('fr', -1)">← Préc.</button>
          <button class="ctrl-btn" onclick="step('fr', 1)">Suiv. →</button>
          <button class="ctrl-btn close" onclick="closeBox('fr')">Fermer ✕</button>
        </div>
      </div>
      <div class="answer-body" id="a-fr"></div>
    </div>

    <div class="grid-5" id="grid-fr"></div>
  </section>

  <!-- BLOC ANGLAIS -->
  <section class="section" id="sec-en">
    <div class="section-header">
      <div class="section-title">🇬🇧 Entretien en Anglais <span class="badge en">15 questions</span></div>
    </div>

    <div class="answer-box en" id="box-en">
      <div class="answer-top">
        <div class="answer-q" id="q-en"></div>
        <div class="answer-controls">
          <button class="ctrl-btn" onclick="step('en', -1)">← Prev.</button>
          <button class="ctrl-btn" onclick="step('en', 1)">Next →</button>
          <button class="ctrl-btn close" onclick="closeBox('en')">Close ✕</button>
        </div>
      </div>
      <div class="answer-body" id="a-en"></div>
    </div>

    <div class="grid-5" id="grid-en"></div>
  </section>
</div>

<script>
const dataFR = [
  {
    q: "1. Pouvez-vous vous présenter ?",
    a: "Bonjour, je m'appelle Mamoun Alami, j'ai 18 ans et je viens du Maroc. Je viens d'obtenir mon baccalauréat avec une mention assez bien.\nJe dirais que je suis quelqu'un d'ambitieux, de curieux et qui aime se fixer des objectifs. J'aime découvrir de nouvelles choses, rencontrer des personnes différentes et sortir de ma zone de confort.\nDepuis mon plus jeune âge, le basketball occupe une place importante dans ma vie. J'ai eu l'occasion d'évoluer dans plusieurs structures sportives au Maroc, notamment à TIBU et au Wydad Casablanca. J'ai participé à différentes compétitions et remporté plusieurs titres. Ces expériences m'ont beaucoup appris, notamment sur la discipline, le travail collectif et la gestion de la pression.\nMais je m'intéresse également à d'autres domaines, notamment au commerce, à l'entrepreneuriat et au monde de l'entreprise. J'aime comprendre comment les organisations fonctionnent et comment les projets se développent.\nAujourd'hui, je souhaite poursuivre mes études en management avec une ambition particulière pour le management sportif. Je recherche une formation qui me permettra de développer des compétences solides tout en gardant une ouverture sur l'international. C'est dans cette démarche que j'ai découvert Audencia, dont le Bachelor correspond particulièrement bien à ce que je souhaite construire pour mon avenir."
  },
  {
    q: "3. Quelles sont vos principales qualités et votre principal défaut ?",
    a: "Si je devais citer trois qualités, je dirais tout d'abord que je suis déterminé. Le sport m'a appris à travailler régulièrement pour atteindre mes objectifs et à ne pas abandonner face aux difficultés.\nJe suis également ambitieux. Quand j'ai un objectif en tête, j'aime chercher les moyens de le concrétiser.\nEnfin, je suis quelqu'un de curieux. Quand un sujet m'intéresse, j'aime obtenir un maximum d'informations et comprendre comment les choses fonctionnent.\nConcernant mon principal défaut, je dirais que je peux être assez têtu. Quand j'ai une idée en tête, j'ai parfois du mal à changer d'avis. Mais j'apprends progressivement à écouter davantage les autres et à comprendre que leurs points de vue peuvent parfois être meilleurs que le mien."
  },
  {
    q: "6. Comment avez-vous réagi à votre échec en Espagne ?",
    a: "Sur le moment, je l'ai forcément mal vécu, parce que c'était un projet qui comptait énormément pour moi.\nMais je pense que la pire chose aurait été de rester bloqué sur cette situation.\nJ'ai donc décidé de prendre du recul, de rechercher d'autres possibilités et surtout de continuer à avancer.\nCette expérience m'a fait comprendre que changer de chemin ne signifie pas forcément abandonner ses ambitions. Aujourd'hui, je considère cette situation comme une étape de mon parcours plutôt que comme un échec qui me définit."
  },
  {
    q: "8. Pourquoi avez-vous choisi Audencia ?",
    a: "J'ai regardé différentes possibilités, mais je ne voulais pas choisir une école uniquement pour son nom ou sa réputation.\nCe qui m'intéresse chez Audencia, c'est la possibilité de suivre une formation généraliste en management et de construire progressivement mon parcours.\nJe souhaite développer des compétences en gestion, en marketing, en commerce et en management, qui pourront ensuite me servir dans mon projet professionnel.\nLa dimension internationale m'intéresse également beaucoup. Je souhaite évoluer dans un environnement où je pourrai rencontrer des personnes avec des parcours différents et développer une autre vision du monde professionnel.\nEnfin, la rentrée décalée correspond à ma situation actuelle et me permettrait de poursuivre mes études sans perdre une année supplémentaire."
  },
  {
    q: "9. Pourquoi le Bachelor en Management et pas une formation spécialisée en management sportif ?",
    a: "Justement parce que je souhaite avoir une vision assez large du management avant de me spécialiser.\nLe management sportif m'intéresse particulièrement, mais je pense qu'il est important de maîtriser les fondamentaux du management, de la gestion, du commerce et de la stratégie.\nUn club sportif reste une organisation qui doit gérer des ressources humaines, des budgets, des partenaires et une stratégie de développement.\nJe préfère donc acquérir ces compétences générales dans un premier temps, puis les mettre à profit dans le secteur qui me passionne."
  },
  {
    q: "10. Pourquoi ne pas avoir choisi une autre école de commerce ?",
    a: "J'ai étudié différentes possibilités, mais je cherchais surtout une formation qui corresponde à mon projet, à ma situation actuelle et à ce que je souhaite devenir.\nCe qui m'a intéressé chez Audencia, c'est la possibilité de construire progressivement mon parcours, d'acquérir des compétences polyvalentes et de bénéficier d'un environnement ouvert sur l'international.\nJe ne voulais pas me spécialiser trop rapidement. Je préfère d'abord découvrir différents domaines du management et développer des bases solides.\nC'est cette cohérence entre mes ambitions et la formation qui a particulièrement retenu mon attention."
  },
  {
    q: "14. Pourquoi le management sportif plutôt que le management classique ?",
    a: "Parce que c'est un domaine dans lequel je peux réunir plusieurs choses qui m'intéressent.\nJ'aime le management, la gestion de projets et le développement des organisations, mais j'ai aussi une véritable connaissance du milieu sportif grâce à mon parcours de basketteur.\nJe trouve intéressant de pouvoir associer ces deux univers.\nCe qui me motive, c'est notamment de comprendre comment un club peut se développer, attirer des partenaires, améliorer son organisation et construire un projet sportif durable."
  },
  {
    q: "16. Pourquoi devrions-nous vous choisir plutôt qu'un autre candidat ?",
    a: "Je pense que mon parcours peut apporter quelque chose de différent.\nJ'ai une expérience du sport de compétition qui m'a appris beaucoup de choses sur le travail, la discipline et le collectif.\nMais je suis également quelqu'un qui souhaite découvrir d'autres domaines, comme l'entrepreneuriat, le monde de l'entreprise et le commerce international.\nJe ne viens pas en considérant que je sais déjà tout. Au contraire, je viens avec l'envie d'apprendre, de m'investir et de profiter pleinement de la formation.\nJe pense que ma détermination et mon parcours m'ont donné une certaine capacité à rebondir et à m'adapter. J'aimerais pouvoir mettre ces qualités au service de la vie étudiante d'Audencia."
  },
  {
    q: "20. Si vous êtes admis, qu'allez-vous apporter à Audencia ?",
    a: "Je pense pouvoir apporter mon expérience, ma personnalité et surtout mon envie de m'investir.\nMon parcours sportif m'a habitué au travail collectif et aux objectifs communs. J'aimerais retrouver cet esprit dans les projets étudiants, les associations et les activités de l'école.\nJe pourrais également apporter un regard différent grâce à mon parcours au Maroc et à mes différentes expériences.\nJe suis quelqu'un qui aime participer, apprendre des autres et partager ses expériences. J'aimerais être un étudiant qui contribue réellement à la vie de son école."
  }
];

const dataEN = [
  {
    q: "1. Can you introduce yourself?",
    a: "Hello, my name is Mamoun Alami. I am 18 years old and I come from Morocco.\nI have recently graduated from high school with good results.\nI would describe myself as an ambitious, curious and determined person. I enjoy discovering new things, meeting new people and learning from different experiences.\nBasketball has been an important part of my life since I was young. I have played for different clubs in Morocco and participated in several competitions.\nToday, I would like to study management because I am interested in business, entrepreneurship and especially sports management.\nMy goal is to develop my skills and build an international career."
  },
  {
    q: "2. Why do you want to study at Audencia?",
    a: "I want to study at Audencia because I am looking for a good business education.\nI like the fact that the Bachelor offers general management courses. I don't want to specialize too early because I want to discover different areas such as marketing, finance and business management.\nI am also interested in the international environment and the opportunities to meet students from different backgrounds.\nI believe Audencia can help me grow both personally and professionally."
  },
  {
    q: "3. Why did you choose business management?",
    a: "I chose business management because I am interested in how companies work and how projects are developed.\nI like understanding how people manage teams, make decisions and develop businesses.\nI also believe that management skills are very important for my future career, especially because I would like to work in sports management.\nI want to learn how to manage an organisation and develop successful projects."
  },
  {
    q: "4. What are your main strengths and weaknesses?",
    a: "I would say that my main strengths are determination, ambition and curiosity.\nWhen I have a goal, I do my best to achieve it. Basketball has taught me discipline and teamwork.\nMy main weakness is that I can sometimes be stubborn. When I have an idea, I sometimes find it difficult to change my mind.\nHowever, I am learning to listen more to other people and consider different opinions."
  },
  {
    q: "5. What is your biggest achievement?",
    a: "One of my biggest achievements is my experience in basketball.\nI had the opportunity to play for important clubs in Morocco, participate in competitions and win several titles.\nI am proud of these experiences because they required a lot of hard work and discipline.\nI also learned how to work with other people and how to deal with pressure."
  },
  {
    q: "6. Tell us about a difficult experience in your life.",
    a: "One difficult experience was my project to join a basketball training centre in Spain.\nUnfortunately, because of visa problems, I could not complete this project.\nI was very disappointed because it was an important goal for me.\nHowever, I decided not to give up. I started looking for other opportunities and thinking about my future.\nThis experience taught me that sometimes things don't happen as planned, but we must keep moving forward."
  },
  {
    q: "7. What is your future career goal?",
    a: "My main career goal is to work in sports management.\nIn the future, I would like to create my own sports organisation, especially in Morocco.\nI believe that basketball in Morocco has a lot of potential, and I would like to help young players find more opportunities to develop their careers.\nI would also like to gain international experience, especially in Europe or the United States."
  },
  {
    q: "8. Why are you interested in entrepreneurship?",
    a: "I am interested in entrepreneurship because I like the idea of creating something from the beginning.\nAn entrepreneur needs to find an opportunity, develop an idea and work hard to make it successful.\nI would like to create my own sports organisation one day.\nI know it requires many skills, such as management, finance, communication and leadership. This is one of the reasons why I want to study business."
  },
  {
    q: "9. What can you bring to Audencia?",
    a: "I think I can bring my experience, my motivation and my personality.\nBecause I come from Morocco, I can share a different cultural background and experiences.\nBasketball has also taught me teamwork, discipline and how to work towards common goals.\nI would like to participate in student associations, sports activities and business projects.\nMost importantly, I am motivated to learn from other students and share my own experiences."
  },
  {
    q: "10. Why should we accept you?",
    a: "I believe I am a motivated and determined student.\nI have different experiences, especially in sports, which have helped me develop important qualities such as discipline, teamwork and resilience.\nI also have clear goals for my future, but I know that I still have a lot to learn.\nI would be very happy to join Audencia, work hard and contribute to the student community."
  },
  {
    q: "11. How do you manage stress?",
    a: "I try to stay calm and focus on what I can control.\nBasketball has taught me how to deal with pressure, especially during important games.\nI also try to organise my work and prepare in advance."
  },
  {
    q: "12. Do you prefer working alone or in a team?",
    a: "I prefer working in a team because I enjoy sharing ideas and learning from other people.\nBasketball has taught me that teamwork is very important to achieve common goals.\nHowever, I can also work independently when necessary."
  },
  {
    q: "13. Why do you want to study abroad?",
    a: "I want to study abroad because I would like to discover a new culture, meet different people and become more independent.\nI also believe that an international experience can help me improve my English and develop new skills."
  },
  {
    q: "14. What do you like doing in your free time?",
    a: "In my free time, I enjoy playing basketball and watching sports.\nI also like discovering new things, following business news and learning about entrepreneurship.\nI enjoy spending time with my family and friends as well."
  },
  {
    q: "15. Where do you see yourself in five years?",
    a: "In five years, I hope to have completed my studies and gained some professional experience.\nI would like to have developed strong management skills and started building my career in sports management.\nI also hope to have international experience and a better understanding of the business world."
  }
];

let currentIdx = { fr: -1, en: -1 };

function renderGrid(lang, items) {
  const grid = document.getElementById('grid-' + lang);
  grid.innerHTML = '';
  items.forEach((item, index) => {
    const btn = document.createElement('button');
    btn.className = 'q-card' + (lang === 'en' ? ' en' : '');
    btn.id = `card-${lang}-${index}`;
    const parts = item.q.split('. ');
    const num = parts[0];
    const text = parts.slice(1).join('. ');
    btn.innerHTML = `<span class="q-num">Q${num}</span><span class="q-text">${text}</span>`;
    btn.onclick = () => selectQuestion(lang, index);
    grid.appendChild(btn);
  });
}

function selectQuestion(lang, index) {
  const items = lang === 'fr' ? dataFR : dataEN;
  if (currentIdx[lang] === index) {
    closeBox(lang);
    return;
  }
  currentIdx[lang] = index;
  document.querySelectorAll(`#grid-${lang} .q-card`).forEach((c, i) => {
    c.classList.toggle('active', i === index);
  });
  document.getElementById('q-' + lang).textContent = items[index].q;
  document.getElementById('a-' + lang).textContent = items[index].a;
  const box = document.getElementById('box-' + lang);
  box.classList.add('visible');
  box.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
}

function step(lang, delta) {
  const items = lang === 'fr' ? dataFR : dataEN;
  let next = currentIdx[lang] + delta;
  if (next < 0) next = items.length - 1;
  if (next >= items.length) next = 0;
  selectQuestion(lang, next);
}

function closeBox(lang) {
  currentIdx[lang] = -1;
  document.getElementById('box-' + lang).classList.remove('visible');
  document.querySelectorAll(`#grid-${lang} .q-card`).forEach(c => c.classList.remove('active'));
}

function filterView(mode, btn) {
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  document.getElementById('sec-fr').style.display = (mode === 'all' || mode === 'fr') ? 'block' : 'none';
  document.getElementById('sec-en').style.display = (mode === 'all' || mode === 'en') ? 'block' : 'none';
}

document.querySelector('.badge').textContent = dataFR.length + ' questions';
document.querySelectorAll('.tab-btn')[1].textContent = 'Français (' + dataFR.length + ')';

renderGrid('fr', dataFR);
renderGrid('en', dataEN);
</script>
</body>
</html>
