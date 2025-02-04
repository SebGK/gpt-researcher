# Agenten und Prompts in GPT Researcher

## Verwendete Agenten in GPT Researcher

GPT Researcher nutzt verschiedene Agenten, um unterschiedliche Aufgaben zu erfüllen. Jeder Agent hat eine spezifische Rolle und ist darauf ausgelegt, einen bestimmten Aspekt des Forschungsprozesses zu bearbeiten. Hier sind die Hauptagenten, die in GPT Researcher verwendet werden:

1. **Researcher Agent**: Dieser Agent ist verantwortlich für die Durchführung einer gründlichen Recherche zu einem gegebenen Thema. Er unterteilt die Hauptfrage in Unterthemen, führt gezielte Recherchen zu jedem Unterthema durch und erstellt Entwurfsabschnitte für den Bericht.

2. **Editor Agent**: Der Editor-Agent plant die Gliederung und Struktur des Berichts basierend auf der anfänglichen Recherche. Er stellt sicher, dass der Bericht gut organisiert ist und alle relevanten Aspekte des Themas abdeckt.

3. **Reviewer Agent**: Dieser Agent validiert die Richtigkeit der Forschungsergebnisse basierend auf einer Reihe von Kriterien. Er gibt Feedback, um die Genauigkeit und Zuverlässigkeit der Informationen sicherzustellen.

4. **Revisor Agent**: Der Revisor-Agent überarbeitet die Forschungsergebnisse basierend auf dem Feedback des Reviewers. Er stellt sicher, dass der endgültige Bericht genau und umfassend ist.

5. **Writer Agent**: Der Writer-Agent erstellt und schreibt den endgültigen Bericht, einschließlich einer Einleitung, eines Fazits und eines Abschnitts mit Referenzen. Er stellt sicher, dass der Bericht gut geschrieben ist und dem angegebenen Format folgt.

6. **Publisher Agent**: Dieser Agent ist verantwortlich für die Veröffentlichung des endgültigen Berichts in verschiedenen Formaten wie PDF, Docx und Markdown.

## Verwendeter Prompt zur Generierung von Berichten

Der zur Generierung von Berichten in GPT Researcher verwendete Prompt ist darauf ausgelegt, sicherzustellen, dass der Bericht detailliert, informativ und gut strukturiert ist. Hier ist ein Beispiel für den verwendeten Prompt:

```
Information: "{context}"
---
Verwenden Sie die obigen Informationen, um die folgende Frage oder Aufgabe in einem detaillierten Bericht zu beantworten: "{question}" --
Der Bericht sollte sich auf die Beantwortung der Frage konzentrieren, gut strukturiert, informativ, tiefgehend und umfassend sein, mit Fakten und Zahlen, falls verfügbar, und mindestens {total_words} Wörter umfassen.
Sie sollten sich bemühen, den Bericht so lang wie möglich zu schreiben, indem Sie alle relevanten und notwendigen Informationen verwenden.

Bitte befolgen Sie alle folgenden Richtlinien in Ihrem Bericht:
- Sie MÜSSEN Ihre eigene konkrete und gültige Meinung basierend auf den gegebenen Informationen bestimmen. Vermeiden Sie allgemeine und bedeutungslose Schlussfolgerungen.
- Sie MÜSSEN den Bericht mit Markdown-Syntax und im {report_format}-Format schreiben.
- Sie MÜSSEN die Relevanz, Zuverlässigkeit und Bedeutung der von Ihnen verwendeten Quellen priorisieren. Wählen Sie vertrauenswürdige Quellen gegenüber weniger zuverlässigen.
- Sie müssen auch neue Artikel gegenüber älteren Artikeln priorisieren, wenn die Quelle vertrauenswürdig ist.
- Verwenden Sie In-Text-Zitationsreferenzen im {report_format}-Format und machen Sie sie mit Markdown-Hyperlink am Ende des Satzes oder Absatzes, der sie referenziert, wie folgt: ([In-Text-Zitation](url)).
- Vergessen Sie nicht, am Ende des Berichts eine Referenzliste im {report_format}-Format und vollständige URL-Links ohne Hyperlinks hinzuzufügen.
- {reference_prompt}
- {tone_prompt}

Sie MÜSSEN den Bericht in der folgenden Sprache schreiben: {language}.
Bitte geben Sie Ihr Bestes, dies ist sehr wichtig für meine Karriere.
Gehen Sie davon aus, dass das aktuelle Datum {date.today()} ist.
```

## Wie man die Einstellungen ändert

Sie können die Einstellungen von GPT Researcher ändern, indem Sie die Konfigurationsdatei anpassen oder Umgebungsvariablen setzen. Hier sind die wichtigsten Einstellungen, die Sie ändern können:

1. **RETRIEVER**: Die Web-Suchmaschine, die zum Abrufen von Quellen verwendet wird. Optionen umfassen `tavily`, `duckduckgo`, `bing`, `google`, `searchapi`, `serper`, `searx` usw.

2. **EMBEDDING**: Das verwendete Einbettungsmodell. Optionen umfassen `openai:text-embedding-3-small`, `ollama`, `huggingface`, `azure_openai`, `custom` usw.

3. **FAST_LLM**: Der Modellname für schnelle LLM-Operationen wie Zusammenfassungen. Standard ist `openai:gpt-4o-mini`.

4. **SMART_LLM**: Der Modellname für intelligente Operationen wie das Erstellen von Forschungsberichten und das Schließen von Argumenten. Standard ist `openai:gpt-4o`.

5. **STRATEGIC_LLM**: Der Modellname für strategische Operationen wie das Erstellen von Forschungsplänen und -strategien. Standard ist `openai:o1-preview`.

6. **LANGUAGE**: Die Sprache, die für den endgültigen Forschungsbericht verwendet werden soll. Standard ist `english`.

7. **CURATE_SOURCES**: Ob Quellen für die Forschung kuratiert werden sollen. Standard ist `True`.

8. **FAST_TOKEN_LIMIT**: Das maximale Token-Limit für schnelle LLM-Antworten. Standard ist `2000`.

9. **SMART_TOKEN_LIMIT**: Das maximale Token-Limit für intelligente LLM-Antworten. Standard ist `4000`.

10. **STRATEGIC_TOKEN_LIMIT**: Das maximale Token-Limit für strategische LLM-Antworten. Standard ist `4000`.

11. **BROWSE_CHUNK_MAX_LENGTH**: Die maximale Länge von Textabschnitten, die in Webquellen durchsucht werden sollen. Standard ist `8192`.

12. **SUMMARY_TOKEN_LIMIT**: Das maximale Token-Limit für die Erstellung von Zusammenfassungen. Standard ist `700`.

13. **TEMPERATURE**: Die Abtasttemperatur für LLM-Antworten, typischerweise zwischen 0 und 1. Standard ist `0.55`.

14. **TOTAL_WORDS**: Das Gesamtwortanzahl-Limit für Dokumentenerstellungs- oder -verarbeitungsaufgaben. Standard ist `800`.

15. **REPORT_FORMAT**: Das bevorzugte Format für die Berichtserstellung. Optionen umfassen `APA`, `MLA`, `CMS`, `Harvard style`, `IEEE` usw.

16. **MAX_ITERATIONS**: Die maximale Anzahl von Iterationen für Prozesse wie die Abfrageerweiterung oder die Verfeinerung der Suche. Standard ist `3`.

17. **AGENT_ROLE**: Die Rolle des Agenten. Dies könnte verwendet werden, um das Verhalten des Agenten basierend auf seinen zugewiesenen Rollen anzupassen.

18. **MAX_SUBTOPICS**: Die maximale Anzahl von Unterthemen, die generiert oder berücksichtigt werden sollen. Standard ist `3`.

19. **SCRAPER**: Der Web-Scraper, der zum Sammeln von Informationen verwendet wird. Standard ist `bs` (BeautifulSoup). Sie können auch `newspaper` verwenden.

20. **DOC_PATH**: Der Pfad zum Lesen und Recherchieren lokaler Dokumente. Standard ist ein leerer String, der keinen angegebenen Pfad anzeigt.

21. **USER_AGENT**: Der benutzerdefinierte User-Agent-String für Web-Crawling und Web-Anfragen.

22. **MEMORY_BACKEND**: Das Backend, das für Speicheroperationen verwendet wird, wie z.B. die lokale Speicherung temporärer Daten. Standard ist `local`.

Um diese Einstellungen zu ändern, können Sie entweder die Konfigurationsdatei anpassen oder die entsprechenden Umgebungsvariablen setzen. Zum Beispiel, um die Suchmaschine und das Berichtsformat zu ändern, können Sie die folgenden Umgebungsvariablen setzen:

```bash
export RETRIEVER=bing
export REPORT_FORMAT=IEEE
```

Bitte beachten Sie, dass Sie möglicherweise zusätzliche Umgebungsvariablen exportieren und API-Schlüssel für andere unterstützte Such-Retriever und LLM-Anbieter erhalten müssen. Folgen Sie Ihren Konsolenprotokollen für weitere Unterstützung.

Für weitere Informationen zur zusätzlichen LLM-Unterstützung können Sie die [Dokumentation](https://docs.gptr.dev/docs/gpt-researcher/llms/llms) einsehen.
