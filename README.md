# Monibank

A three-step account-opening flow for a fictional digital bank, in HTML, CSS and vanilla JavaScript. You fill in a registration form with real validation, take a photo with your webcam, and reach a confirmation page. There is also a landing page that promotes the bank.

**Live demo:** [monibank-theta-ten.vercel.app](https://monibank-theta-ten.vercel.app)

## What's inside

- **Form validation without a library.** Each required field is checked on `blur` with the browser's Constraint Validation API, and a message from a lookup table is shown under the field. Name, email, RG and the terms checkbox use patterns and types.
- **CPF check.** `valida-cpf.js` implements the Brazilian CPF algorithm: it rejects repeated-digit numbers and verifies both check digits.
- **Age check.** `valida-idade.js` blocks anyone under 18, based on the birth date.
- **Webcam capture.** `camera.js` asks for camera access with `getUserMedia`, shows the live video, draws a frame onto a `<canvas>` when you click, and keeps the image as a JPEG data URL.
- **Multi-step state.** The answers from step 1 are stored in `localStorage`, and step 2 adds the photo to the same record before moving on to step 3. The scripts are ES modules.

The interface is in Portuguese. This is a simulation, so the registration is never sent to a server.

## Run it

The camera only works on `localhost` or HTTPS, and ES modules need a server, so use one:

```bash
git clone https://github.com/victorhubarb/monibank.git
cd monibank
python3 -m http.server 8000     # then open http://localhost:8000
```

## Project structure

```
index.html              Landing page
pages/                  The three steps of the sign-up flow
js/                     script.js, valida-cpf.js, valida-idade.js, camera.js
styles/                 Shared, landing page and form styles
```

## Known gaps

- The photo is only captured, not analyzed. There is no face verification.
- The form data and the photo are kept unencrypted in `localStorage`. That is fine for a demo and not something to do with real personal data.
- The header links are placeholders.

---

Victor Hugo Barbosa · [GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
