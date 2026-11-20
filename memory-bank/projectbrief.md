# Project brief: Nexova Solutions

Source of truth: [BRIEFING.md](../BRIEFING.md).

## 1. Company

Human resources and talent selection consultancy founded in 2011. Headquarters in Valencia (Spain) and an office in Miami. 120 employees, about 8 million dollars a year. Lines: headhunting of middle managers and executives, outsourcing of customer support teams, and training in soft skills and leadership. Clients: mid-sized technology, retail and financial services companies that outsource their talent management.

## 2. Problem

Nexova cannot operate at scale: manual work and disconnected tools, with no telemetry or centralised logs. Consequences: consultants on automatable tasks, clients without visibility into their processes, an invisible training catalogue, support that misses its Service Level Agreement (SLA) and management working with week-old data. Urgency: automated platforms already compete directly and the window is limited.

## 3. Areas and needs

Details in [BRIEFING.md](../BRIEFING.md#the-departments-and-their-problems).

| Area                                  | Manager                                         | Main need                                                   |
| ------------------------------------- | ----------------------------------------------- | ----------------------------------------------------------- |
| Talent Selection Operations           | Javier Almeida                                  | Automatic scoring and ranking of curriculum vitae (CV)      |
| Corporate Training                    | Elena Vargas                                    | Catalogue with online enrolment and programme recommendation |
| Customer Support (outsourced service) | Roberto Díaz                                    | Chatbot that resolves 40% of queries without human intervention |
| Sales and Business Development        | Megan Clarke or Marcos Ibáñez (to be confirmed) | Automated prospecting and follow-up alerts                  |
| Marketing and Communications          | Carmen Ruiz                                     | Redesigned website and conversion measurement               |
| Human Resources (Internal)            | Patricia Solís                                  | Internal portal with automated onboarding                   |
| Technology and Infrastructure         | Sergio Molina                                   | Telemetry, centralised logging and data pipeline            |
| Executive Direction                   | Laura Mendoza                                   | Unified real-time dashboard                                 |

## 4. Project goals

Systems, automations and intelligent tools so that Nexova does what it already does well faster, at greater scale and with less manual effort.

- **By area**: dashboards on a common data pipeline, portals (candidates, learners, employees), automations with alerts and sentiment analysis of tickets.
- **Artificial intelligence (AI) capabilities**: CV scoring and ranking; Retrieval-Augmented Generation (RAG) over the candidate database and in the support chatbot; semantic search over the support knowledge base; training programme recommendation; AI-assisted content; agents for candidate emails, sales proposals, Human Resources queries, training plans, technical architecture and natural-language management queries.

## 5. Business constraints

- **Support SLA**: 24 h committed; 48 h on average today (BRIEFING.md › Customer Support (outsourced service)).
- **Personal data** of candidates and employees: never real in the repository, logs or prompts; fictitious in development. _Inference_: operates in the European Union (BRIEFING.md › introduction) and handles personal data.
- **Decisions about people**: AI proposes (scoring, rankings, responses); a person decides or receives what the AI does not resolve. _Inference_: chatbot that resolves only 40% without human intervention (BRIEFING.md › Customer Support (outsourced service)).

## 6. Known inconsistencies and ambiguities

- **Sales manager**: Megan Clarke (BRIEFING.md › How the company is organised) vs Marcos Ibáñez (BRIEFING.md › Sales and Business Development). To be confirmed.
- **Corporate Training**: recommendation by client company profile (BRIEFING.md › Corporate Training, explicit); are the chatbot's "personalised plans" per company or per learner? To be confirmed.
