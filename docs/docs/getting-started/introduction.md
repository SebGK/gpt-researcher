# Einführung

[![Offizielle Website](https://img.shields.io/badge/Official%20Website-gptr.dev-teal?style=for-the-badge&logo=world&logoColor=white)](https://gptr.dev)
[![Discord Follow](https://dcbadge.vercel.app/api/server/QgZXvJAccX?style=for-the-badge&theme=clean-inverted)](https://discord.gg/QgZXvJAccX)

[![GitHub Repo stars](https://img.shields.io/github/stars/assafelovic/gpt-researcher?style=social)](https://github.com/assafelovic/gpt-researcher)
[![Twitter Follow](https://img.shields.io/twitter/follow/assaf_elovic?style=social)](https://twitter.com/assaf_elovic)
[![PyPI version](https://badge.fury.io/py/gpt-researcher.svg)](https://badge.fury.io/py/gpt-researcher)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/assafelovic/gpt-researcher/blob/master/docs/docs/examples/pip-run.ipynb)

**[GPT Researcher](https://gptr.dev) ist ein autonomer Agent, der für umfassende Online-Recherchen zu verschiedenen Aufgaben entwickelt wurde.** 

Der Agent kann detaillierte, faktenbasierte und unvoreingenommene Forschungsberichte erstellen, mit Anpassungsoptionen für die Fokussierung auf relevante Ressourcen, Gliederungen und Lektionen. Inspiriert von den jüngsten [Plan-and-Solve](https://arxiv.org/abs/2305.04091) und [RAG](https://arxiv.org/abs/2005.11401) Papieren, adressiert GPT Researcher Probleme wie Geschwindigkeit, Determinismus und Zuverlässigkeit, indem er eine stabilere Leistung und erhöhte Geschwindigkeit durch parallelisierte Agentenarbeit bietet, im Gegensatz zu synchronen Operationen.

## Warum GPT Researcher?

- Um objektive Schlussfolgerungen für manuelle Forschungsaufgaben zu ziehen, kann es Zeit in Anspruch nehmen, manchmal Wochen, um die richtigen Ressourcen und Informationen zu finden.
- Aktuelle LLMs sind auf vergangene und veraltete Informationen trainiert, mit hohen Risiken von Halluzinationen, was sie für Forschungsaufgaben fast irrelevant macht.
- Aktuelle LLMs sind auf kurze Token-Ausgaben beschränkt, die nicht ausreichen, um lange detaillierte Forschungsberichte (über 2.000 Wörter) zu erstellen.
- Lösungen, die Websuche ermöglichen (wie ChatGPT + Web Plugin), berücksichtigen nur begrenzte Ressourcen und Inhalte, die in einigen Fällen zu oberflächlichen Schlussfolgerungen oder voreingenommenen Antworten führen.
- Die Verwendung nur einer Auswahl von Ressourcen kann zu Voreingenommenheit bei der Bestimmung der richtigen Schlussfolgerungen für Forschungsfragen oder -aufgaben führen. 

## Architektur
Die Hauptidee ist es, "Planungs-" und "Ausführungs-" Agenten auszuführen, wobei der Planer Fragen zur Recherche generiert und die Ausführungsagenten die relevantesten Informationen basierend auf jeder generierten Forschungsfrage suchen. Schließlich filtert und aggregiert der Planer alle relevanten Informationen und erstellt einen Forschungsbericht. <br /> <br /> 
Die Agenten nutzen sowohl gpt-4o-mini als auch gpt-4o (128K Kontext), um eine Forschungsaufgabe abzuschließen. Wir optimieren die Kosten, indem wir jeden nur bei Bedarf verwenden. **Die durchschnittliche Forschungsaufgabe dauert etwa 3 Minuten und kostet ~0,1 $.**

<div align="center">
<img align="center" height="600" src="https://github.com/assafelovic/gpt-researcher/assets/13554167/4ac896fd-63ab-4b77-9688-ff62aafcc527" />
</div>


Genauer gesagt:
* Erstellen Sie einen domänenspezifischen Agenten basierend auf der Forschungsfrage oder -aufgabe.
* Generieren Sie eine Reihe von Forschungsfragen, die zusammen eine objektive Meinung zu einer gegebenen Aufgabe bilden. 
* Für jede Forschungsfrage einen Crawler-Agenten auslösen, der Online-Ressourcen nach Informationen durchsucht, die für die gegebene Aufgabe relevant sind.
* Für jede gesammelte Ressource eine Zusammenfassung basierend auf relevanten Informationen erstellen und die Quellen im Auge behalten.
* Schließlich alle zusammengefassten Quellen filtern und aggregieren und einen abschließenden Forschungsbericht erstellen.

## Demo
<iframe height="400" width="700" src="https://github.com/assafelovic/gpt-researcher/assets/13554167/a00c89a6-a295-4dd0-b58d-098a31c40fda" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## Tutorials
 - [Video Tutorial Series](https://www.youtube.com/playlist?list=PLUGOUZPIB0F-qv6MvKq3HGr0M_b3U2ATv)
 - [How it Works](https://medium.com/better-programming/how-i-built-an-autonomous-ai-agent-for-online-research-93435a97c6c)
 - [How to Install](https://www.loom.com/share/04ebffb6ed2a4520a27c3e3addcdde20?sid=da1848e8-b1f1-42d1-93c3-5b0b9c3b24ea)
 - [Live Demo](https://www.loom.com/share/6a3385db4e8747a1913dd85a7834846f?sid=a740fd5b-2aa3-457e-8fb7-86976f59f9b8)
 - [Homepage](https://gptr.dev)

## Funktionen
- 📝 Generieren von Forschungs-, Gliederungs-, Ressourcen- und Lektionenberichten
- 📜 Kann lange und detaillierte Forschungsberichte (über 2.000 Wörter) erstellen
- 🌐 Aggregiert über 20 Webquellen pro Forschung, um objektive und faktenbasierte Schlussfolgerungen zu ziehen
- 🖥️ Enthält eine benutzerfreundliche Weboberfläche (HTML/CSS/JS)
- 🔍 Durchsucht Webquellen mit JavaScript-Unterstützung
- 📂 Behält den Überblick und den Kontext der besuchten und verwendeten Webquellen
- 📄 Exportiert Forschungsberichte in PDF, Word und mehr...

Lass uns [hier](/docs/gpt-researcher/getting-started/getting-started) loslegen!

## Zusätzliche Ressourcen
- [Agenten und Prompts](../agents_and_prompts.md)
