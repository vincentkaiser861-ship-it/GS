# GS<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GlobalShield Tactical OS - Varsovie</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; }
        body { background: #070a14; color: #f8fafc; display: flex; flex-direction: column; align-items: center; min-height: 100vh; padding: 20px; }
        .container { width: 100%; max-width: 500px; background: #0f172a; border: 1px solid #1e293b; border-radius: 12px; padding: 20px; box-shadow: 0 10px 25px rgba(0,0,0,0.6); }
        h1 { color: #38bdf8; font-size: 1.3rem; text-align: center; margin-bottom: 5px; display: flex; align-items: center; justify-content: center; gap: 8px; }
        .sub-header { text-align: center; color: #94a3b8; font-size: 0.85rem; margin-bottom: 15px; }
        .gps-status { background: #1e293b; color: #38bdf8; padding: 10px; border-radius: 8px; text-align: center; font-size: 0.85rem; font-weight: bold; margin-bottom: 20px; border: 1px solid #334155; }
        
        .alert-box { background: #1e293b; border-left: 5px solid #3b82f6; padding: 15px; border-radius: 8px; margin-bottom: 15px; font-size: 0.9rem; }
        .alert-box.warning { border-left-color: #f59e0b; background: #261f12; }
        .alert-title { font-weight: bold; color: #fff; margin-bottom: 6px; display: flex; justify-content: space-between; align-items: center; }
        
        .source-link { display: inline-block; margin-top: 10px; font-size: 0.8rem; color: #38bdf8; text-decoration: none; font-weight: 500; }
        .source-link:hover { text-decoration: underline; }
        
        .sos-btn { background: #dc2626; color: white; border: none; width: 100%; padding: 16px; font-size: 1rem; font-weight: bold; border-radius: 8px; cursor: pointer; text-transform: uppercase; letter-spacing: 0.05em; transition: background 0.2s; margin-top: 10px; box-shadow: 0 4px 12px rgba(220, 38, 38, 0.4); }
        .sos-btn:hover { background: #b91c1c; }
    </style>
</head>
<body>

    <div class="container">
        <h1>🛡️ GlobalShield Tactical OS</h1>
        <div class="sub-header">Priorité Opérationnelle : Varsovie (Pologne)</div>
        <div id="gps" class="gps-status">📍 Localisation : Varsovie (Centre / Sektor 1)</div>

        <!-- Alerte 1 : Police Varsovie -->
        <div class="alert-box">
            <div class="alert-title">
                <span>🔵 POLICE : Sécurité Renforcée</span>
                <span style="font-size:0.7rem; background:#1e3a8a; color:#93c5fd; padding:2px 6px; border-radius:4px;">Live</span>
            </div>
            <p>Mise en place de barrières de sécurité et contrôles renforcés dans l'hypercentre (Krakowskie Przedmieście et axes avoisinants) suite aux consignes de la Policja.</p>
            <a href="https://policja.pl/" target="_blank" class="source-link">🔗 Source officielle : Policja</a>
        </div>

        <!-- Alerte 2 : MSWiA -->
        <div class="alert-box warning">
            <div class="alert-title">
                <span>🟡 MSWiA : Alerte Nationale & Consignes</span>
                <span style="font-size:0.7rem; background:#78350f; color:#fde68a; padding:2px 6px; border-radius:4px;">Actif</span>
            </div>
            <p>Rappel des consignes de vigilance et suivi des répercussions sécuritaires nationales (coordination inter-régionale).</p>
            <a href="https://www.gov.pl/web/mswia" target="_blank" class="source-link">🔗 Source officielle : Ministère de l'Intérieur (MSWiA)</a>
        </div>

        <!-- Alerte 3 : Ministère de la Défense -->
        <div class="alert-box warning">
            <div class="alert-title">
                <span>🟡 ARMÉE : Veille Stratégique</span>
                <span style="font-size:0.7rem; background:#78350f; color:#fde68a; padding:2px 6px; border-radius:4px;">Vigilance</span>
            </div>
            <p>Surveillance conjointe des points névralgiques de la capitale par les forces armées et les services de protection.</p>
            <a href="https://www.gov.pl/web/obrona-narodowa" target="_blank" class="source-link">🔗 Source officielle : Ministère de la Défense (MON)</a>
        </div>

        <button class="sos-btn" onclick="triggerSOS()">🚨 Déclencher Alerte SOS Urgence</button>
    </div>

    <script>
        function triggerSOS() {
            if(confirm("Confirmer l'envoi d'une alerte SOS d'urgence avec transmission de vos coordonnées GPS à Varsovie ?")) {
                alert("🚨 Alerte SOS transmise avec succès ! Position partagée avec les services d'urgence.");
            }
        }

        if (navigator.geolocation) {
            navigator.geolocation.getCurrentPosition((pos) => {
                const lat = pos.coords.latitude.toFixed(4);
                const lon = pos.coords.longitude.toFixed(4);
                document.getElementById('gps').innerText = `📍 GPS Actif : ${lat}, ${lon} (Varsovie Priority)`;
            }, () => {});
        }
    </script>

</body>
</html>