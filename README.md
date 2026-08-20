# Minor_project_1
Python tool for analyzing WhatsApp chat data. Features file uploading, message parsing, stop-word frequency filtering, response time tracking, and inactive streak measurement. Generates ASCII activity heatmaps, group member behavioral archetypes (Night Owl, Spammer, Ghost), and key chat activity insights.

# GroupDNA: WhatsApp Chat Analytics & Behavioral Profiling
GroupDNA is an automated Python pipeline for parsing raw WhatsApp group chat logs to extract usage statistics, temporal activity patterns, and user behavioral archetypes.

## ❓ Question & Project Brief
How can raw WhatsApp chat logs (`hostel_bois.txt`) be parsed and analyzed to uncover communication patterns, response times, active hours, and member behavioral personas?

## ⚠️ The Problem
Exported WhatsApp chat logs contain unformatted text, system notifications, deleted message placeholders, and media tags. Manually sifting through thousands of messages to calculate user activity, peak chatting times, or response speeds is inefficient and error-prone.

## 💡 The Solution
GroupDNA automates the parsing and analysis process. It filters out irrelevant lines, processes message timestamps, maps group chat intensity over time, measures response latencies, and uses heuristic criteria to profile user behaviors.

## 🛠️ Libraries Used
* **`numpy`**: Constructs and manages 2D matrices (7-day by 24-hour grid) for temporal heatmaps.
* **`datetime`**: Parses message timestamps, computes response gaps in seconds, and groups messages by day/hour.
* **`zipfile` & `os**`: Handles extraction of compressed chat data archives and file path management.
* **`google.colab`**: Manages interactive file uploads within Google Colab.

## ⚙️ How We Solve the Problem
1. **Data Extraction & Parsing:** Reads text lines, merges multi-line messages, and filters out deleted text or media markers.
2. **Frequency Analysis:** Tokenizes text, strips common stop words, and visualizes word frequencies using ASCII bars.
3. **Temporal Heatmap Generation:** Populates a 7x24 activity grid and prints a shaded ASCII heatmap in 3-hour blocks.
4. **Latency & Silence Tracking:** Calculates time delays between messages from different senders to determine average response speeds and longest inactive streaks.
5. **Archetype Classification:** Categorizes users using predefined logic rules:
* **NIGHT OWL:** >60% of messages sent between 10 PM and 5 AM.
* **STORYTELLER:** Average message length >25 words.
* **DRAMA QUEEN:** Sent more than 30 all-caps messages.
* **SPAMMER:** Sent over 500 total messages.
* **GHOST:** Sent fewer than 50 total messages.
