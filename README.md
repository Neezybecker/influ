<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Influgix Consulting Group</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            overflow-x: hidden;
        }
        header {
            background-color: #333;
            color: #fff;
            padding: 1em 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.7));
            z-index: 1;
            opacity: 0;
            transition: opacity 0.5s ease;
        }
        header:hover::before {
            opacity: 1;
        }
        h1, h2 {
            color: #333;
            text-align: center;
        }
        h1 {
            position: relative;
            z-index: 2;
        }
        p {
            position: relative;
            z-index: 2;
        }
        main {
            padding: 1em 2em;
            animation: fadeIn 1s ease-in-out;
        }
        section {
            margin-bottom: 2em;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeUp 1s ease forwards;
        }
        section:nth-child(2) {
            animation-delay: 0.5s;
        }
        section:nth-child(3) {
            animation-delay: 1s;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            background: #fff;
            margin: 0.5em 0;
            padding: 1em;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        li:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
        }
        .contact {
            text-align: center;
        }
        .contact a {
            color: #3498db;
            text-decoration: none;
            transition: color 0.3s ease;
        }
        .contact a:hover {
            color: #2980b9;
        }
        .contact-form {
            background: #fff;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            max-width: 600px;
            margin: 20px auto;
            position: relative;
            overflow: hidden;
        }
        .contact-form::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 0;
            background: #3498db;
            z-index: 1;
            transition: height 0.5s ease;
        }
        .contact-form:hover::before {
            height: 100%;
        }
        .contact-form form {
            position: relative;
            z-index: 2;
        }
        .contact-form input, .contact-form textarea {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ddd;
            transition: border-color 0.3s ease;
        }
        .contact-form input:focus, .contact-form textarea:focus {
            border-color: #3498db;
        }
        .contact-form button {
            padding: 10px 20px;
            background: #333;
            color: #fff;
            border: none;
            cursor: pointer;
            transition: background 0.3s ease;
        }
        .contact-form button:hover {
            background: #555;
        }
        .contact-form button:active {
            transform: scale(0.95);
        }
        footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 1em 0;
            position: relative;
            width: 100%;
        }
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
        @keyframes fadeUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>Influgix Consulting Group</h1>
        <p>Votre partenaire de confiance pour l'immigration</p>
    </header>
    <main>
        <section>
            <h2>Nos Services</h2>
            <p>Nous offrons des services d'immigration spécialisés pour différents besoins :</p>
            <ul>
                <li>Immigration pour étudiants</li>
                <li>Immigration pour travailleurs</li>
                <li>Immigration pour touristes</li>
            </ul>
        </section>
        <section class="contact">
            <h2>Contactez-nous</h2>
            <p>Pour plus d'informations, visitez notre page Facebook :</p>
            <p><a href="https://web.facebook.com/Neezybeck" target="_blank">Influgix Consulting Group sur Facebook</a></p>
        </section>
        <section class="contact-form">
            <h2>Formulaire de Contact</h2>
            <form id="contactForm">
                <input type="text" id="name" placeholder="Votre nom" required>
                <input type="email" id="email" placeholder="Votre email" required>
                <textarea id="message" rows="5" placeholder="Votre message" required></textarea>
                <button type="submit">Envoyer</button>
            </form>
            <p id="formStatus"></p>
        </section>
    </main>
    <footer>
        <p>&copy; 2024 Influgix Consulting Group. Tous droits réservés.</p>
    </footer>

    <script>
        document.getElementById('contactForm').addEventListener('submit', function(event) {
            event.preventDefault();
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;
            const status = document.getElementById('formStatus');
            
            if (name && email && message) {
                status.textContent = 'Merci, ' + name + '! Votre message a été envoyé.';
                status.style.color = 'green';
                setTimeout(() => {
                    status.textContent = '';
                    document.getElementById('contactForm').reset();
                }, 5000);
            } else {
                status.textContent = 'Veuillez remplir tous les champs.';
                status.style.color = 'red';
            }
        });
    </script>
</body>
</html>
