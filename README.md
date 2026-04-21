<!doctype html>
<html lang="fr">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Comparatif — Solutions site internet Mairie de Charvonnex</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family:
                system-ui,
                -apple-system,
                sans-serif;
            background: #f9f8f6;
            color: #1a1a1a;
            padding: 2rem;
        }

        .header {
            padding: 1.5rem 0 1rem;
            border-bottom: 0.5px solid #ddd;
            margin-bottom: 1.5rem;
        }

        .header h1 {
            font-size: 22px;
            font-weight: 500;
            color: #1a1a1a;
        }

        .header p {
            font-size: 13px;
            color: #666;
            margin-top: 4px;
        }

        .filter-bar {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
            margin-bottom: 1.5rem;
            align-items: center;
        }

        .filter-label {
            font-size: 12px;
            color: #666;
            margin-right: 4px;
        }

        .filter-btn {
            font-size: 12px;
            padding: 4px 12px;
            border-radius: 20px;
            border: 0.5px solid #ccc;
            background: #fff;
            color: #555;
            cursor: pointer;
            transition: all 0.15s;
        }

        .filter-btn.active {
            background: #185fa5;
            border-color: #185fa5;
            color: #fff;
        }

        .filter-btn:hover:not(.active) {
            background: #f0f0f0;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1rem;
        }

        .card {
            background: #fff;
            border: 0.5px solid #ddd;
            border-radius: 12px;
            padding: 1rem 1.25rem;
            cursor: pointer;
            transition: border-color 0.15s;
        }

        .card:hover {
            border-color: #999;
        }

        .card.expanded {
            border-color: #185fa5;
        }

        .card.recommended {
            border: 2px solid #185fa5;
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 10px;
        }

        .card-title {
            font-size: 15px;
            font-weight: 500;
            color: #1a1a1a;
        }

        .card-subtitle {
            font-size: 12px;
            color: #666;
            margin-top: 2px;
        }

        .badge {
            font-size: 11px;
            padding: 3px 8px;
            border-radius: 4px;
            white-space: nowrap;
        }

        .badge-current {
            background: #eaf3de;
            color: #3b6d11;
        }

        .badge-wordpress {
            background: #e6f1fb;
            color: #185fa5;
        }

        .badge-74 {
            background: #faeeda;
            color: #854f0b;
        }

        .badge-tout-en-un {
            background: #faeeda;
            color: #854f0b;
        }

        .badge-mobile-only {
            background: #faeeda;
            color: #854f0b;
        }

        .badge-DIY {
            background: #faeeda;
            color: #854f0b;
        }

        .cost {
            font-size: 20px;
            font-weight: 500;
            color: #1a1a1a;
        }

        .cost-sub {
            font-size: 12px;
            color: #666;
        }

        .score-row {
            display: flex;
            gap: 6px;
            margin: 10px 0;
        }

        .score-item {
            flex: 1;
            text-align: center;
        }

        .score-label {
            font-size: 10px;
            color: #666;
            margin-bottom: 3px;
        }

        .score-dots {
            display: flex;
            gap: 2px;
            justify-content: center;
        }

        .dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: #ddd;
        }

        .dot.on {
            background: #185fa5;
        }

        .features-row {
            display: flex;
            flex-wrap: wrap;
            gap: 4px;
            margin: 8px 0;
        }

        .feat {
            font-size: 11px;
            padding: 2px 7px;
            border-radius: 3px;
            display: flex;
            align-items: center;
            gap: 3px;
        }

        .feat-ok {
            background: #eaf3de;
            color: #3b6d11;
        }

        .feat-no {
            background: #fcebeb;
            color: #a32d2d;
        }

        .feat-partial {
            background: #faeeda;
            color: #854f0b;
        }

        .expand-btn {
            font-size: 12px;
            color: #185fa5;
            background: none;
            border: none;
            cursor: pointer;
            padding: 4px 0;
            display: flex;
            align-items: center;
            gap: 4px;
            margin-top: 8px;
        }

        .detail-section {
            border-top: 0.5px solid #ddd;
            margin-top: 12px;
            padding-top: 12px;
            display: none;
        }

        .card.expanded .detail-section {
            display: block;
        }

        .detail-group {
            margin-bottom: 10px;
        }

        .detail-title {
            font-size: 11px;
            font-weight: 500;
            color: #888;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            margin-bottom: 4px;
        }

        .detail-list {
            list-style: none;
        }

        .detail-list li {
            font-size: 12px;
            color: #1a1a1a;
            padding: 2px 0;
            display: flex;
            gap: 6px;
        }

        .detail-list li:before {
            content: "→";
            color: #aaa;
            flex-shrink: 0;
        }

        .pro:before {
            content: "+";
            color: #3b6d11 !important;
        }

        .con:before {
            content: "−";
            color: #a32d2d !important;
        }

        .link-row {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            margin-top: 6px;
        }

        .ext-link {
            font-size: 11px;
            color: #185fa5;
            text-decoration: none;
            padding: 2px 8px;
            border: 0.5px solid #b5d4f4;
            border-radius: 3px;
        }

        .ext-link:hover {
            background: #e6f1fb;
        }

        .legend {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            margin-bottom: 1rem;
        }

        .legend-item {
            display: flex;
            align-items: center;
            gap: 5px;
            font-size: 11px;
            color: #666;
        }

        .legend-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
        }
    </style>
</head>

<body>
    <div class="header">
        <h1>Comparatif — Solutions site internet pour Charvonnex</h1>
        <p>
            Présentation pour le Conseil Municipal · 2026 · Cliquer sur une
            carte pour voir le détail
        </p>
    </div>

    <div class="filter-bar">
        <span class="filter-label">Filtrer :</span>
        <button class="filter-btn active" onclick="filterCards('all', this)">
            Toutes les solutions
        </button>
        <button class="filter-btn" onclick="filterCards('badge:current', this)">
            Solution actuelle
        </button>
        <button class="filter-btn" onclick="filterCards('badge:74', this)">
            Local Haute-Savoie
        </button>
        <button class="filter-btn" onclick="filterCards('badge:tout-en-un', this)">
            Tout-en-un
        </button>
        <button class="filter-btn" onclick="filterCards('badge:WordPress', this)">
            WordPress
        </button>
        <button class="filter-btn" onclick="filterCards('badge:DIY', this)">
            DIY
        </button>
        <p>
            <span class="filter-label" style="margin-left: 8px">Fonctionnalités :</span>
            <button class="filter-btn" onclick="filterCards('newsletter', this)">
                Newsletter
            </button>
            <button class="filter-btn" onclick="filterCards('chatbot', this)">
                Chatbot
            </button>
            <button class="filter-btn" onclick="filterCards('mobile', this)">
                App mobile
            </button>
            <button class="filter-btn" onclick="filterCards('ia', this)">
                Visibilité IA
            </button>
            <button class="filter-btn" onclick="filterCards('boîte à idées', this)">
                Boîte à idées / sondages
            </button>
        </p>
    </div>

    <div class="legend">
        <div class="legend-item">
            <div class="legend-dot" style="background: #185fa5"></div>
            Présent
        </div>
        <div class="legend-item">
            <div class="legend-dot" style="background: #ef9f27"></div>
            Partiel / option payante
        </div>
        <div class="legend-item">
            <div class="legend-dot" style="background: #ddd"></div>
            Absent
        </div>
    </div>

    <div class="grid" id="grid"></div>

    <script>
        const FEATURES = [
            "non-tech",
            "newsletter",
            "CR lisibles",
            "visib. IA",
            "app mobile",
            "chatbot",
            "boîte à idées",
            "domaine .fr",
        ];
        const solutions = [
            {
                id: "reseau",
                title: "Réseau des Communes",
                subtitle: "Solution actuelle · Neopse",
                badge: "current",
                badgeLabel: "Solution actuelle",
                cost: "~600€",
                costSub: "par an (estimation)",
                scores: { facilite: 4, setup: 5, modif: 4 },
                features: {
                    "non-tech": 1,
                    "newsletter": 1,
                    "CR lisibles": 0,
                    "visib. IA": 0,
                    "app mobile": 1,
                    "chatbot": 0,
                    "boîte à idées": 1,
                    "domaine .fr": 0,
                },
                tags: ["newsletter", "mobile", "boîte à idées"],
                pros: [
                    "Déjà en place, aucune migration",
                    "Support inclus",
                    "Adapté aux communes",
                ],
                cons: [
                    "Domaine .com non conforme RPNT",
                    "Propriété du prestataire, pas de la commune",
                    "Design daté, peu personnalisable",
                    "CR PDF non lisibles en ligne",
                    "Chatbot absent",
                    "Visibilité IA faible",
                    "Pas de boîte à idées ni sondages",
                ],
                links: [
                    {
                        label: "recherche Google de site utilisant le réseaudescommunes",
                        url: "https://www.google.com/search?q=site%3Aneopse-site.com&client=ubuntu-chr&hs=E6x&sca_esv=b2aed787d8e0833f&sxsrf=ANbL-n5nICkS5b6gpkCcCBrEhIc-IpE1cw%3A1774802113980&ei=wVTJae28O7ibkdUP04DzgQE&biw=960&bih=504&ved=0ahUKEwitobOMxcWTAxW4TaQEHVPAPBAQ4dUDCBE&uact=5&oq=site%3Aneopse-site.com&gs_lp=Egxnd3Mtd2l6LXNlcnAiFHNpdGU6bmVvcHNlLXNpdGUuY29tSLkGUABYAHAAeAGQAQCYATigATiqAQExuAEDyAEA-AEC-AEBmAIAoAIAmAMAkgcAoActsgcAuAcAwgcAyAcAgAgA&sclient=gws-wiz-serp",
                    },
                ],
                note: "Le domaine mairie-charvonnex.com appartient au prestataire, pas à la commune. Risque de dépendance.",
            },
            {
                id: "spip",
                title: "SPIP / ADM74",
                subtitle: "Association des Maires de Haute-Savoie",
                badge: "74",
                badgeLabel: "Local Haute-Savoie",
                cost: "650€ H.T.",
                costSub: "cotisation ADM74",
                scores: { facilite: 3, setup: 4, modif: 3 },
                features: {
                    "non-tech": 1,
                    "newsletter": 1,
                    "CR lisibles": 1,
                    "visib. IA": 0,
                    "app mobile": 0,
                    "chatbot": 0,
                    "boîte à idées": 0,
                    "domaine .fr": 1,
                },
                tags: ["newsletter"],
                pros: [
                    "Support local dédié (équipe Haute-Savoie)",
                    "~40 communes utilisatrices en 74",
                    "Conforme RPNT et RGPD",
                    "Domaine .fr possible",
                ],
                cons: [
                    "Design peu moderne, personnalisation limitée",
                    "Pas de chatbot IA",
                    "Pas d'app mobile",
                    "Visibilité IA faible",
                    "Newsletter basique",
                    "Pas de boîte à idées ni sondages",
                    "Coût à clarifier avec ADM74",
                ],
                links: [{ label: "Annuaire site adm74", url: "https://www.maires74.asso.fr/sites-internet/" }],
                note: "Solution rassurante par sa proximité géographique.",
            },
            {
                id: "intramuros",
                title: "Intramuros",
                subtitle: "Site + app mobile + panneaux",
                badge: "Tout-en-un",
                badgeLabel: "Tout-en-un",
                cost: "~150€",
                costSub: "par mois (~1 800€/an)",
                scores: { facilite: 5, setup: 5, modif: 5 },
                features: {
                    "non-tech": 1,
                    "newsletter": 1,
                    "CR lisibles": 1,
                    "visib. IA": 0,
                    "app mobile": 1,
                    "chatbot": 0,
                    "boîte à idées": 1,
                    "domaine .fr": 1,
                },
                tags: ["newsletter", "mobile", "sondages","boîte à idées"],
                pros: [
                    "App mobile native avec notifications push",
                    "Interface très simple pour les secrétaires",
                    "Panneau d'affichage numérique inclus",
                    "Support client dédié communes",
                    "Sondages / votes citoyens disponibles (selon forfait)",
                ],
                cons: [
                    "Coût mensuel élevé",
                    "Chatbot absent",
                    "Visibilité IA faible",
                    "Dépendance à un éditeur privé",
                    "Moins flexible qu'un WordPress",
                ],
                links: [
                    {
                        label: "Carte des communes utilisant Intramuros",
                        url: "https://www.intramuros.org/carte",
                    },

                ],
                note: "Solution idéale si l'app mobile avec notifications et la connxion au panneu d'informations digitale est une priorité absolue.",
            },
            {
                id: "illiwap",
                title: "Illiwap",
                subtitle: "Site + app mobile + panneaux",
                badge: "Tout-en-un",
                badgeLabel: "Tout-en-un",
                cost: "~100–200€",
                costSub: "par mois (selon options)",
                scores: { facilite: 4, setup: 4, modif: 4 },
                features: {
                    "non-tech": 1,
                    "newsletter": 1,
                    "CR lisibles": 1,
                    "visib. IA": 0,
                    "app mobile": 1,
                    "chatbot": 0,
                    "boîte à idées": 1,
                    "domaine .fr": 1,
                },
                tags: ["newsletter", "mobile", "boîte à idées"],
                pros: [
                    "App mobile avec notifications push",
                    "Panneaux d'affichage connectés",
                    "Utilisé par de nombreuses communes rurales",
                    "Tout géré par le prestataire",
                    "Sondages / votes citoyens disponibles (selon forfait)",
                ],
                cons: [
                    "Coût mensuel récurrent élevé",
                    "Chatbot absent",
                    "Visibilité IA limitée",
                    "Personnalisation design limitée",
                ],
                links: [
                    {
                        label: "Carte des communes utilisan illiwap",
                        url: "https://www.illiwap.com/fr/references",
                    },
                ],
                note: "Concurrent direct d'Intramuros. Comparer les tarifs et les références locales avant de décider.",
            },
            {
                id: "panneaupocket",
                title: "Panneau Pocket",
                subtitle: "Application mobile uniquement",
                badge: "Mobile-only",
                badgeLabel: "Mobile only",
                cost: "~0–50€",
                costSub: "par mois",
                scores: { facilite: 5, setup: 5, modif: 5 },
                features: {
                    "non-tech": 1,
                    "newsletter": 0,
                    "CR lisibles": 0,
                    "visib. IA": 0,
                    "app mobile": 1,
                    "chatbot": 0,
                    "boîte à idées": 0,
                    "domaine .fr": 0,
                },
                tags: ["mobile"],
                pros: [
                    "Très simple d'utilisation",
                    "App mobile avec notifications",
                    "Gratuit ou très peu cher",
                    "Large adoption dans les communes rurales",
                ],
                cons: [
                    "Pas de site internet",
                    "Pas de domaine .fr conforme RPNT",
                    "Pas de chatbot",
                    "CR non lisibles en ligne",
                    "Ne remplace pas un site web",
                    "Pas de boîte à idées ni sondages",
                ],
                links: [
                    {
                        label: "Carte des communes utilisant panneaupocket.fr",
                        url: "https://app.panneaupocket.com/",
                    },
                ],
                note: "Solution complémentaire, pas de remplacement. Peut se combiner avec un site WordPress.",
            },
            {
                id: "wp-freelance",
                title: "WordPress + Freelance",
                subtitle: "Site sur-mesure, hébergement français",
                badge: "WordPress",
                badgeLabel: "WordPress",
                cost: "~500–2000€",
                costSub: "création + ~100€/an hébergement",
                scores: { facilite: 4, setup: 3, modif: 4 },
                features: {
                    "non-tech": 1,
                    "newsletter": 1,
                    "CR lisibles": 1,
                    "visib. IA": 1,
                    "app mobile": 1,
                    "chatbot": 1,
                    "boîte à idées": 1,
                    "domaine .fr": 1,
                },
                tags: ["newsletter", "chatbot", "ia", "mobile", "boîte à idées"],
                pros: [
                    "Totalement personnalisable",
                    "chatbot IA intégrable (Claude API)",
                    "Newsletter via Brevo (gratuit)",
                    "Conforme RPNT, RGPD, RGAA",
                    "Hébergement français (o2switch)",
                    "Domaine charvonnex.fr via ANCT",
                    "CR affichables en ligne sans PDF",
                    "Boîte à idées / sondages / votes intégrables via plugin (ex. WPForms)",
                ],
                cons: [
                    "Nécessite un freelance de confiance",
                    "Délais variables selon disponibilité",
                    "App mobile = développement supplémentaire (coût)",
                ],
                links: [
                    {
                        label: "Freelance WordPress - Yb-webcreation- Annecy- Haute-Savoie",
                        url: "https://www.yb-webcreation.fr/",
                    },
                    {
                        label: "o2switch.fr",
                        url: "https://www.o2switch.fr",
                    },
                ],
                note: "Meilleur rapport qualité/prix. Solution retenue comme référence. Inspirée de La Clusaz (Créasit).",
            },
            {
                id: "wp-agence",
                title: "WordPress + Agence",
                subtitle: "Site sur-mesure par une agence web",
                badge: "WordPress",
                badgeLabel: "WordPress",
                cost: "200~15000€?",
                costSub: "création + maintenance annuelle",
                scores: { facilite: 4, setup: 2, modif: 4 },
                features: {
                    "non-tech": 1,
                    "newsletter": 1,
                    "CR lisibles": 1,
                    "visib. IA": 1,
                    "app mobile": 1,
                    "chatbot": 1,
                    "boîte à idées": 1,
                    "domaine .fr": 1,
                },
                tags: ["newsletter", "chatbot", "ia", "mobile", "boîte à idées"],
                pros: [
                    "Résultat professionnel garanti",
                    "Accompagnement complet",
                    "Garantie contractuelle",
                    "Maintenance incluse possible",
                    "Boîte à idées / sondages / votes intégrables sur mesure",
                ],
                cons: [
                    "Coût très élevé pour une commune de ~1000 habitants",
                    "Délais 3–6 mois",
                    "Dépendance à l'agence pour les modifications techniques",
                ],
                links: [
                    {
                        label: "Exemple : laclusaz.org (Créasit)",
                        url: "https://www.laclusaz.org",
                    },
                    { label: "monclocher.com", url: "https://www.monclocher.com/references/#filtre" },
                    { label: "commu-net.fr", url: "https://www.commu-net.fr" },
                    { label: "mapetitemairie.fr", url: "https://www.mapetitemairie.fr" },
                    { label: "creasit.fr", url: "https://www.creasit.fr" }
                ],
                note: "Qualité maximale mais coût disproportionné. Justifiable si subvention DETR ou dotation numérique.",
            },
            {
                id: "vibecoding",
                title: "Vibe Coding (Claude Code…)",
                subtitle: "Développement IA assisté",
                badge: "DIY",
                badgeLabel: "DIY",
                cost: "~200–500€",
                costSub: "abonnement IA + hébergement",
                scores: { facilite: 2, setup: 2, modif: 2 },
                features: {
                    "non-tech": 0,
                    "newsletter": 1,
                    "CR lisibles": 1,
                    "visib. IA": 1,
                    "app mobile": 1,
                    "chatbot": 1,
                    "boîte à idées": 1,
                    "domaine .fr": 1,
                },
                tags: ["newsletter", "chatbot", "ia", "mobile", "boîte à idées"],
                pros: [
                    "Techniquement très flexible",
                    "Coût de développement réduit",
                    "Toutes les fonctionnalités possibles",
                    "Site entièrement sur-mesure",
                    "Boîte à idées / sondages / votes entièrement personnalisables",
                ],
                cons: [
                    "Nécessite des compétences techniques importantes",
                    "Maintenance complexe pour des non-développeurs",
                    "Risque de bugs si pas suivi",
                    "Pas adapté pour une mairie sans développeur en interne",
                ],
                links: [
                    {
                        label: "claude.ai/code",
                        url: "https://claude.ai/code",
                    },
                ],
                note: "Solution puissante mais inadaptée si aucun développeur n'est disponible en interne sur le long terme.",
            },
        ];

        function dots(score, max = 5) {
            let html = '<div class="score-dots">';
            for (let i = 1; i <= max; i++)
                html += `<div class="dot${i <= score ? " on" : ""}"></div>`;
            return html + "</div>";
        }

        function featBadge(val, label) {
            if (val === 1)
                return `<span class="feat feat-ok">✓ ${label}</span>`;
            if (val === 2)
                return `<span class="feat feat-partial">~ ${label}</span>`;
            return `<span class="feat feat-no">✗ ${label}</span>`;
        }

        function renderCards(filtered) {
            const grid = document.getElementById("grid");
            grid.innerHTML = "";
            filtered.forEach((s) => {
                const card = document.createElement("div");
                card.className =
                    "card" +
                    (s.badge === "recommended" ? " recommended" : "");
                card.dataset.id = s.id;
                card.innerHTML = `
            <div class="card-header">
              <div>
                <div class="card-title">${s.title}</div>
                <div class="card-subtitle">${s.subtitle}</div>
              </div>
              ${s.badge ? `<span class="badge badge-${s.badge}">${s.badgeLabel}</span>` : ""}
            </div>
            <div style="margin-bottom:8px">
              <span class="cost">${s.cost}</span>
              <span class="cost-sub"> ${s.costSub}</span>
            </div>
            <div class="score-row">
              <div class="score-item"><div class="score-label">Facilité utilisation</div>${dots(s.scores.facilite)}</div>
              <div class="score-item"><div class="score-label">Mise en place</div>${dots(s.scores.setup)}</div>
              <div class="score-item"><div class="score-label">Modifications</div>${dots(s.scores.modif)}</div>
            </div>
            <div class="features-row">
              ${FEATURES.map((f) => featBadge(s.features[f], f)).join("")}
            </div>
            <button class="expand-btn" onclick="toggleCard('${s.id}', this)">Voir le détail ↓</button>
            <div class="detail-section">
              <div class="detail-group">
                <div class="detail-title">Avantages</div>
                <ul class="detail-list">${s.pros.map((p) => `<li class="pro">${p}</li>`).join("")}</ul>
              </div>
              <div class="detail-group">
                <div class="detail-title">Inconvénients</div>
                <ul class="detail-list">${s.cons.map((c) => `<li class="con">${c}</li>`).join("")}</ul>
              </div>
              ${s.note ? `<div style="font-size:12px;color:#555;background:#f5f5f5;padding:8px 10px;border-radius:6px;border-left:3px solid #378ADD;margin-bottom:8px">${s.note}</div>` : ""}
              <div class="link-row">${s.links.map((l) => `<a class="ext-link" href="${l.url}" target="_blank">${l.label} ↗</a>`).join("")}</div>
            </div>`;
                grid.appendChild(card);
            });
        }

        function toggleCard(id, btn) {
            const card = document.querySelector(`.card[data-id="${id}"]`);
            const expanded = card.classList.toggle("expanded");
            btn.textContent = expanded
                ? "Masquer le détail ↑"
                : "Voir le détail ↓";
        }

        function filterCards(tag, btn) {
            document
                .querySelectorAll(".filter-btn")
                .forEach((b) => b.classList.remove("active"));
            btn.classList.add("active");
            let filtered;
            if (tag === "all") {
                filtered = solutions;
            } else if (tag.startsWith("badge:")) {
                const badgeVal = tag.slice(6);
                filtered = solutions.filter((s) => s.badge === badgeVal);
            } else {
                filtered = solutions.filter((s) => (s.tags || []).includes(tag));
            }
            renderCards(filtered);
        }

        renderCards(solutions);
    </script>
</body>

</html>
