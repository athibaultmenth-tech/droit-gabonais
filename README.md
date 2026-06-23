# <!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ConsoGabon — Média Juridique Citoyen & Assistant IA</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&family=Lora:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bleu:#1A3C6E;--bleu-deep:#0F2547;--bleu-pale:#EBF1FA;
  --vert:#1A7A4A;--vert-pale:#E8F5EE;
  --rouge:#C0392B;--rouge-pale:#FBEAE8;
  --or:#D4A017;--or-pale:#FDF6E3;
  --violet:#6B3FA0;--violet-pale:#F0EBF9;
  --fond:#F8F9FC;--fond2:#F0F2F8;--blanc:#FFFFFF;
  --encre:#1C1E26;--muted:#5A6070;--muted2:#8A92A0;
  --line:#E2E5ED;--line2:#CBD0DC;
  --r:10px;--r2:6px;
  --shadow:0 2px 8px rgba(26,60,110,.08),0 1px 2px rgba(26,60,110,.04);
  --shadow-md:0 4px 20px rgba(26,60,110,.12),0 2px 6px rgba(26,60,110,.06);
}
body{font-family:'Plus Jakarta Sans',sans-serif;font-size:15px;color:var(--encre);background:var(--fond);-webkit-font-smoothing:antialiased}
a{color:var(--bleu);text-decoration:none}
button{cursor:pointer;font-family:'Plus Jakarta Sans',sans-serif}
h1,h2,h3,h4{font-family:'Plus Jakarta Sans',sans-serif;font-weight:700;line-height:1.2}

/* HEADER EXTENDED FOR MEDIA VISION */
.hdr{background:var(--bleu-deep);padding:0 24px;position:sticky;top:0;z-index:100;box-shadow:0 2px 12px rgba(0,0,0,.2)}
.hdr-in{display:flex;align-items:center;justify-content:space-between;max-width:1300px;margin:0 auto;height:68px;gap:12px}
.brand{display:flex;align-items:center;gap:10px;cursor:pointer}
.logo{width:40px;height:40px;background:linear-gradient(135deg,var(--or),#E8B820);border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:16px;font-weight:800;color:var(--bleu-deep);flex-shrink:0}
.brand-txt .name{font-size:18px;font-weight:800;color:#fff;letter-spacing:-.2px}
.brand-txt .tag{font-size:10px;color:rgba(255,255,255,.5);letter-spacing:.04em;text-transform:uppercase}
nav{display:flex;gap:1px;flex-wrap:wrap}
nav button{background:none;border:none;color:rgba(255,255,255,.7);padding:8px 12px;border-radius:6px;font-size:13px;font-weight:500;transition:all 0.15s}
nav button:hover{background:rgba(255,255,255,.1);color:#fff}
nav button.act{background:rgba(255,255,255,.15);color:#fff;font-weight:600}
.hdr-cta{background:linear-gradient(135deg, var(--or), #E8B820);color:var(--bleu-deep);border:none;padding:8px 16px;border-radius:6px;font-size:13px;font-weight:700;white-space:nowrap;flex-shrink:0}
.hdr-cta:hover{transform:translateY(-1px)}

/* HERO */
.hero{background:linear-gradient(135deg,var(--bleu-deep) 0%,#1A3C6E 55%,#1A5C8E 100%);padding:50px 24px 44px;position:relative;overflow:hidden}
.hero-in{max-width:1300px;margin:0 auto;display:grid;grid-template-columns:1fr 400px;gap:44px;align-items:center;position:relative}
@media(max-width:960px){.hero-in{grid-template-columns:1fr}.hero-side{display:none}}
.hero h1{font-size:clamp(26px,3.8vw,40px);color:#fff;line-height:1.2;margin-bottom:12px;font-weight:800}
.hero h1 em{color:var(--or);font-style:normal}
.hero p{font-size:15px;color:rgba(255,255,255,.75);max-width:55ch;margin-bottom:20px;line-height:1.6}
.hero-stats{display:flex;gap:20px;margin-top:20px}
.hstat{color:rgba(255,255,255,.6);font-size:12px}
.hstat strong{color:#fff;font-size:20px;display:block}

/* SIDE PANEL */
.hero-side{background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.1);border-radius:12px;padding:18px;backdrop-filter:blur(8px)}
.hside-title{color:var(--or);font-size:11px;text-transform:uppercase;letter-spacing:.05em;margin-bottom:12px;font-weight:700}
.feed-item{border-left:2px solid var(--or);padding-left:12px;margin-bottom:12px;cursor:pointer}
.feed-item h5{color:#fff;font-size:13px;font-weight:600}
.feed-item span{color:rgba(255,255,255,.4);font-size:11px}

/* SEARCH & FILTERS */
.searchbar{background:var(--blanc);border-bottom:1px solid var(--line);padding:14px 24px;box-shadow:var(--shadow)}
.sb-in{max-width:1300px;margin:0 auto;display:flex;gap:12px}
.sb-wrap{flex:1;display:flex;border:1.5px solid var(--line2);border-radius:var(--r2);overflow:hidden;background:var(--fond)}
.sb-wrap input{flex:1;border:none;background:transparent;padding:10px 14px;font-size:14px;outline:none}

/* CONTENT ARCHITECTURE */
.main{max-width:1300px;margin:0 auto;padding:32px 24px 80px}
.grid-layout{display:grid;grid-template-columns:repeat(auto-fill, minmax(320px, 1fr));gap:20px;margin-top:16px}
.premium-badge{position:absolute;top:12px;right:12px;background:var(--bleu-deep);color:var(--or);border:1px solid var(--or);padding:3px 8px;border-radius:4px;font-size:10px;font-weight:700;text-transform:uppercase}

/* MEDIA CARDS */
.m-card{background:var(--blanc);border:1px solid var(--line);border-radius:var(--r);overflow:hidden;position:relative;transition:all 0.2s;box-shadow:var(--shadow);cursor:pointer}
.m-card:hover{transform:translateY(-2px);box-shadow:var(--shadow-md)}
.m-card-body{padding:20px}
.m-card-cat{font-size:10px;font-weight:800;text-transform:uppercase;color:var(--bleu);margin-bottom:8px;display:block}
.m-card h3{font-size:16px;color:var(--bleu-deep);margin-bottom:8px}
.m-card p{font-size:13px;color:var(--muted);line-height:1.6}

/* CHATBOX IA */
.chat-container{background:var(--blanc);border:1px solid var(--line);border-radius:var(--r);max-width:800px;margin:0 auto;overflow:hidden;box-shadow:var(--shadow-md)}
.chat-hdr{background:var(--bleu-deep);color:#fff;padding:16px 20px;display:flex;align-items:center;gap:12px}
.chat-body{height:400px;overflow-y:auto;padding:20px;background:#f4f6fa;display:flex;flex-direction:column;gap:12px}
.msg{max-width:75%;padding:12px 16px;border-radius:12px;font-size:14px;line-height:1.5}
.msg.user{background:var(--bleu);color:#fff;align-self:flex-end;border-bottom-right-radius:2px}
.msg.ai{background:var(--blanc);color:var(--encre);align-self:flex-start;border-bottom-left-radius:2px;border:1px solid var(--line)}
.chat-input-area{padding:12px;background:var(--blanc);border-top:1px solid var(--line);display:flex;gap:8px}
.chat-input-area input{flex:1;border:1.5px solid var(--line2);border-radius:var(--r2);padding:10px;outline:none}

/* PREMIUM ACCESS PLATFORM */
.prem-box{max-width:900px;margin:0 auto;background:var(--blanc);border:2px solid var(--or);border-radius:12px;overflow:hidden;box-shadow:var(--shadow-md)}
.prem-hdr{background:linear-gradient(135deg, var(--bleu-deep), #163561);color:#fff;padding:32px;text-align:center}
.prem-body{padding:32px;display:grid;grid-template-columns:1fr 1fr;gap:32px}
@media(max-width:640px){.prem-body{grid-template-columns:1fr}}
.momo-btn{width:100%;background:#FFCC00;color:#000;border:none;padding:14px;border-radius:8px;font-weight:800;font-size:15px;margin-top:12px;display:flex;align-items:center;justify-content:center;gap:10px}

/* DASHBOARD FOR SIMULATED FIREBASE/BACKEND MANAGEMENT */
.db-box{background:#111622;color:#fff;padding:16px;border-radius:8px;font-family:monospace;font-size:12px;margin-top:40px}
.db-tag{background:var(--vert);color:#fff;padding:2px 6px;border-radius:4px;font-size:9px;font-weight:bold}

/* FOOTER */
footer{background:var(--bleu-deep);color:rgba(255,255,255,.5);padding:40px 24px 20px;margin-top:60px;border-top:4px solid var(--or)}
.foot-in{max-width:1300px;margin:0 auto;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:20px}
</style>
</head>
<body>

<div id="app">
  <header class="hdr">
    <div class="hdr-in">
      <div class="brand" @click="currentView = 'home'">
        <div class="logo">CG</div>
        <div class="brand-txt">
          <div class="name">ConsoGabon</div>
          <div class="tag">Média & Intelligence Juridique</div>
        </div>
      </div>
      <nav>
        <button :class="{act: currentView === 'home'}" @click="currentView = 'home'">Accueil</button>
        <button :class="{act: currentView === 'actu'}" @click="currentView = 'actu'">Actualités</button>
        <button :class="{act: currentView === 'articles'}" @click="currentView = 'articles'">Articles pratiques</button>
        <button :class="{act: currentView === 'textes'}" @click="currentView = 'textes'">Textes juridiques</button>
        <button :class="{act: currentView === 'jurisprudence'}" @click="currentView = 'jurisprudence'">Jurisprudence</button>
        <button :class="{act: currentView === 'faq'}" @click="currentView = 'faq'">Questions/Réponses</button>
        <button :class="{act: currentView === 'ia'}" @click="currentView = 'ia'">🤖 Assistant IA</button>
        <button :class="{act: currentView === 'premium'}" @click="currentView = 'premium'" style="color:var(--or)">⭐ Premium</button>
      </nav>
      <button class="hdr-cta" @click="currentView = 'contact'">Contact</button>
    </div>
  </header>

  <section class="hero" v-if="currentView === 'home'">
    <div class="hero-in">
      <div>
        <h1>Le premier média du droit <br><em>gabonais accessible à tous.</em></h1>
        <p>Suivez les actualités législatives, consultez les textes de loi officiels et interrogez notre intelligence artificielle formée sur les codes de la République Gabonaise.</p>
        <div class="hero-stats">
          <div class="hstat"><strong>5 400+</strong>Citoyens aidés</div>
          <div class="hstat"><strong>250+</strong>Textes & Décisions</div>
          <div class="hstat"><strong>En continu</strong>Mises à jour Législatives</div>
        </div>
      </div>
      <div class="hero-side">
        <div class="hside-title">⚡ Flash Actualités</div>
        <div class="feed-item" @click="currentView = 'actu'">
          <h5>Réforme du Code du Travail</h5>
          <span>Il y a 2 heures • Actualités</span>
        </div>
        <div class="feed-item" @click="currentView = 'premium'">
          <h5>Espace Premium Actif</h5>
          <span>Modèles de contrats via Mobile Money</span>
        </div>
      </div>
    </div>
  </section>

  <div class="searchbar" v-if="['home', 'actu', 'articles', 'textes', 'jurisprudence'].includes(currentView)">
    <div class="sb-in">
      <div class="sb-wrap">
        <input type="text" v-model="searchQuery" placeholder="Rechercher instantanément un article, une actualité, une jurisprudence...">
      </div>
    </div>
  </div>

  <main class="main">
    
    <div v-if="currentView === 'home'">
      <h2>À la une aujourd'hui</h2>
      <div class="grid-layout">
        <div class="m-card" @click="currentView = 'actu'">
          <div class="m-card-body">
            <span class="m-card-cat">Actualités</span>
            <h3>Contrôles des prix à Libreville et Akanda</h3>
            <p>La direction générale de la Concurrence et de la Consommation accentue la surveillance sur les produits de première nécessité.</p>
          </div>
        </div>
        <div class="m-card" @click="currentView = 'articles'">
          <div class="m-card-body">
            <span class="m-card-cat">Articles Pratiques</span>
            <h3>Loyer abusif : quels recours pour le locataire au Gabon ?</h3>
            <p>Découvrez comment contester une hausse unilatérale supérieure au plafond légal fixé par le Code civil.</p>
          </div>
        </div>
        <div class="m-card" @click="currentView = 'ia'">
          <div class="m-card-body" style="background: var(--bleu-pale)">
            <span class="m-card-cat">Assistant IA</span>
            <h3>Une question sur le Code du Travail ?</h3>
            <p>Posez directement votre cas pratique à notre intelligence artificielle connectée aux textes officiels.</p>
          </div>
        </div>
      </div>
    </div>

    <div v-if="currentView === 'actu'">
      <h2>Actualités Juridiques & Économiques au Gabon</h2>
      <div class="grid-layout">
        <div class="m-card" v-for="item in filteredActus">
          <div class="m-card-body">
            <span class="m-card-cat">Gabon • {{item.date}}</span>
            <h3>{{item.title}}</h3>
            <p>{{item.desc}}</p>
          </div>
        </div>
      </div>
    </div>

    <div v-if="currentView === 'articles'">
      <h2>Guides et Fiches Pratiques Citoyennes</h2>
      <div class="grid-layout">
        <div class="m-card" v-for="art in filteredArticles">
          <div class="m-card-body">
            <span class="m-card-cat">{{art.cat}}</span>
            <h3>{{art.title}}</h3>
            <p>{{art.desc}}</p>
          </div>
        </div>
      </div>
    </div>

    <div v-if="currentView === 'textes'">
      <h2>Codes et Textes de Lois Officiels de la République</h2>
      <div class="grid-layout">
        <div class="m-card" v-for="t in filteredTextes">
          <div class="m-card-body">
            <span class="m-card-cat">Journal Officiel</span>
            <h3>{{t.title}}</h3>
            <p>Version consolidée officielle. Statut : Vigueur.</p>
          </div>
        </div>
      </div>
    </div>

    <div v-if="currentView === 'jurisprudence'">
      <h2>Décisions et Jurisprudences des Tribunaux Gabonais</h2>
      <p style="color:var(--muted); margin-bottom: 20px;">Retrouvez l'orientation des sentences pour anticiper vos chances de succès.</p>
      <div class="grid-layout">
        <div class="m-card" v-for="j in filteredJurisprudence">
          <div class="m-card-body">
            <span class="m-card-cat">Tribunal de {{j.place}}</span>
            <h3>{{j.title}}</h3>
            <p><strong>Décision :</strong> {{j.outcome}}</p>
          </div>
        </div>
      </div>
    </div>

    <div v-if="currentView === 'faq'">
      <h2>Questions fréquentes de l'espace Communauté</h2>
      <div class="grid-layout" style="grid-template-columns: 1fr;">
        <div class="m-card" v-for="f in faqs" style="cursor: default;">
          <div class="m-card-body">
            <h3 style="color:var(--bleu)">❓ {{f.q}}</h3>
            <p style="margin-top: 10px; font-family: 'Lora', serif; font-style: italic;">👉 {{f.a}}</p>
          </div>
        </div>
      </div>
    </div>

    <div v-if="currentView === 'ia'">
      <div class="chat-container">
        <div class="chat-hdr">
          <div style="font-size: 24px;">🤖</div>
          <div>
            <h4>Assistant Juridique ConsoGabon IA</h4>
            <p style="font-size: 11px; color: rgba(255,255,255,0.7)">Alimenté par les Codes Gabonais (Travail, Civil, Pénal)</p>
          </div>
        </div>
        <div class="chat-body" id="chatBody">
          <div class="msg ai">Bonjour ! Je suis votre consultant juridique IA. Posez-moi votre question (ex: "Quel est le préavis légal pour un licenciement après 2 ans d'ancienneté ?").</div>
          <div class="msg" v-for="m in chatMessages" :class="m.role === 'user' ? 'user' : 'ai'">{{m.text}}</div>
          <div class="msg ai" v-if="aiTyping">⚡ Traitement de la requête via OpenAI API...</div>
        </div>
        <div class="chat-input-area">
          <input type="text" v-model="userQuery" placeholder="Posez votre question juridique ici..." @keyup.enter="triggerAiResponse">
          <button class="form-submit" @click="triggerAiResponse" style="background:var(--bleu); color:#fff; border:none; padding:10px 20px; border-radius:6px; font-weight:bold;">Envoyer</button>
        </div>
      </div>
    </div>

    <div v-if="currentView === 'premium'">
      <div class="prem-box">
        <div class="prem-hdr">
          <span style="font-size: 12px; font-weight: 800; color: var(--or); text-transform: uppercase; letter-spacing: 1px">Abonnement Professionnel</span>
          <h2 style="font-size: 28px; margin-top: 5px;">Débloquez l'accès Premium Intégral</h2>
          <p style="opacity: 0.8; font-size: 14px; margin-top: 8px;">Téléchargement illimité de modèles de contrats rédigés par des avocats agréés au Gabon.</p>
        </div>
        <div class="prem-body">
          <div>
            <h4 style="margin-bottom: 12px;">Ce que vous obtenez :</h4>
            <ul style="margin-left: 20px; color: var(--muted); line-height: 1.8">
              <li>Modèles de baux d'habitation conformes 2026</li>
              <li>Modèles de contrats de travail (CDI, CDD, Essai)</li>
              <li>Générateur automatique de mise en demeure</li>
              <li>Consultations prioritaires avec l'IA</li>
            </ul>
          </div>
          <div style="background: var(--fond); padding: 20px; border-radius: 8px; text-align: center">
            <h3 style="font-size: 24px; color: var(--bleu-deep)">5 000 FCFA <span style="font-size: 14px; color: var(--muted)">/ mois</span></h3>
            <p style="font-size: 12px; color: var(--muted); margin: 8px 0 16px">Paiement sécurisé instantané local</p>
            
            <button class="momo-btn" @click="simulatePayment('Airtel Money')">
              📱 Payer via Airtel Money
            </button>
            <button class="momo-btn" style="background:#EE3124; color:#fff" @click="simulatePayment('Moov Money')">
              📱 Payer via Moov Money
            </button>
          </div>
        </div>
      </div>
    </div>

    <div v-if="currentView === 'contact'">
      <div style="max-width: 600px; margin: 0 auto; background: #fff; padding: 30px; border-radius: 8px; box-shadow: var(--shadow);">
        <h2>Contacter la Rédaction & Soumettre un texte</h2>
        <p style="color: var(--muted); margin: 10px 0 20px;">Vous êtes juriste ou avocat au Gabon ? Rejoignez notre réseau de contributeurs pour ajouter des articles sans coder via notre CMS Firebase.</p>
        <div style="margin-bottom: 15px;">
          <label style="display:block; font-weight:bold; margin-bottom:5px;">Nom complet</label>
          <input type="text" style="width:100%; padding:10px; border:1px solid var(--line2); border-radius:6px;">
        </div>
        <div style="margin-bottom: 15px;">
          <label style="display:block; font-weight:bold; margin-bottom:5px;">Message ou proposition de partenariat</label>
          <textarea style="width:100%; padding:10px; border:1px solid var(--line2); border-radius:6px; min-height:100px;"></textarea>
        </div>
        <button class="form-submit" style="width:100%; background:var(--bleu); color:#fff; border:none; padding:12px; border-radius:6px; font-weight:bold;" @click="alert('Message envoyé avec succès à la rédaction !')">Envoyer</button>
      </div>
    </div>

    <div class="db-box">
      <div>⚙️ <span class="db-tag">PROJECTION ARCHITECTURALE DURABLE ACTIVE</span></div>
      <p style="margin-top: 8px; color: #a0aec0">
        Pour éviter le fichier HTML monolithique obsolète, l'implémentation future de l'App se structurera ainsi :
        <br>• <strong>React Client :</strong> Composants réutilisables découplés (Fiches, Chat, Abonnements).
        <br>• <strong>Firebase Firestore :</strong> Collection <code style="color:var(--or)">/articles</code> et <code style="color:var(--or)">/actus</code> pour publication via interface administrative sans code.
        <br>• <strong>Firebase Auth :</strong> Protection native des routes de l'Espace Premium.
        <br>• <strong>Edge Functions Vercel :</strong> Passerelle sécurisée masquant vos clés API secrètes OpenAI et jetons agrégateurs Mobile Money.
      </p>
    </div>

  </main>

  <footer>
    <div class="foot-in">
      <div>
        <h4 style="color:#fff; margin-bottom:4px;">ConsoGabon Média</h4>
        <p>Le droit vulgarisé au service du peuple gabonais.</p>
      </div>
      <div style="font-size: 12px;">
        © 2026 ConsoGabon. Tous droits réservés. Déploiement optimisé Vercel.
      </div>
    </div>
  </footer>
</div>

<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
<script>
  const { createApp } = Vue;

  createApp({
    data() {
      return {
        currentView: 'home',
        searchQuery: '',
        userQuery: '',
        aiTyping: false,
        chatMessages: [],
        
        // BASE JURIDIQUE DE DONNÉES DU MÉDIA
        actus: [
          { title: "Lancement de la caravane nationale de contrôle des prix", desc: "La DGCC annonce le déploiement d'inspecteurs assermentés sur les marchés de l'Estuaire.", date: "23 Juin 2026" },
          { title: "Nouveau barème d'indemnisation du licenciement abusif", desc: "Les tribunaux du travail harmonisent les grilles de calcul pour plus de transparence envers les salariés.", date: "15 Juin 2026" }
        ],
        articles: [
          { title: "Rupture de la période d'essai au Gabon : obligations de l'employeur", desc: "Durée maximale, renouvellement unique et formalisme du délai de prévenance selon le Code du Travail.", cat: "Droit du Travail" },
          { title: "Restitution de caution de logement : les pièges à éviter", desc: "Modèle d'état des lieux contradictoire et délais légaux impartis au bailleur pour restituer l'argent.", cat: "Logement" }
        ],
        textes: [
          { title: "Loi n° 022/2021 du 19 novembre 2021 portant Code du Travail en République Gabonaise" },
          { title: "Code Civil Gabonais — Titre VIII : Du contrat de louage" }
        ],
        jurisprudence: [
          { title: "Licenciement économique sans autorisation préalable de l'inspection", place: "Libreville", outcome: "Nullité du licenciement ordonnée et réintégration immédiate du salarié sous astreinte." }
        ],
        faqs: [
          { q: "Mon bailleur peut-il couper l'eau ou l'électricité pour impayé ?", a: "Non. Même en cas de non-paiement du loyer, la coupure sauvage de services essentiels par le bailleur constitue une voie de fait répréhensible devant le juge des référés." }
        ]
      }
    },
    computed: {
      filteredActus() {
        return this.actus.filter(i => i.title.toLowerCase().includes(this.searchQuery.toLowerCase()));
      },
      filteredArticles() {
        return this.articles.filter(i => i.title.toLowerCase().includes(this.searchQuery.toLowerCase()));
      },
      filteredTextes() {
        return this.textes.filter(i => i.title.toLowerCase().includes(this.searchQuery.toLowerCase()));
      },
      filteredJurisprudence() {
        return this.jurisprudence.filter(i => i.title.toLowerCase().includes(this.searchQuery.toLowerCase()));
      }
    },
    methods: {
      triggerAiResponse() {
        if(!this.userQuery.trim()) return;
        
        // Add User Message
        this.chatMessages.push({ role: 'user', text: this.userQuery });
        const query = this.userQuery;
        this.userQuery = '';
        this.aiTyping = true;
        
        // Scroll to view
        setTimeout(() => {
          const body = document.getElementById('chatBody');
          body.scrollTop = body.scrollHeight;
        }, 50);

        // Simulate API call processing OpenAI completion
        setTimeout(() => {
          this.aiTyping = false;
          let aiText = "D'après l'analyse des textes juridiques gabonais en vigueur, votre situation relève des dispositions de la loi. Pour un avis optimal, veuillez vous munir de vos pièces justificatives matérielles.";
          
          if(query.toLowerCase().includes('préavis') || query.toLowerCase().includes('travail')) {
            aiText = "Selon l'Article 65 du Code du Travail Gabonais, la résiliation du contrat de travail est subordonnée à un préavis écrit notifié par la partie qui prend l'initiative de la rupture. La durée varie selon la catégorie professionnelle et l'ancienneté (généralement 1 à 3 mois).";
          } else if(query.toLowerCase().includes('caution') || query.toLowerCase().includes('loyer')) {
            aiText = "Le Code Civil limite la caution contractuelle à deux mois de loyer. Le bailleur dispose d'un mois après la remise des clés pour restituer ce dépôt, déduction faite des éventuelles dégradations justifiées par état des lieux.";
          }

          this.chatMessages.push({ role: 'assistant', text: aiText });
          
          setTimeout(() => {
            const body = document.getElementById('chatBody');
            body.scrollTop = body.scrollHeight;
          }, 50);
        }, 1500);
      },
      simulatePayment(operator) {
        alert(`Initialisation de la passerelle API ${operator}...\n\nMontant : 5 000 FCFA\nDemande de saisie du code PIN envoyée sur votre mobile.\n\n(Démonstration d'intégration du flux financier de l'espace Premium).`);
      }
    }
  }).mount('#app');
</script>
</body>
</html>droit-gabonais
