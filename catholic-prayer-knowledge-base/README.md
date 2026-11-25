# Grace — Catholic Prayer Fellowship Knowledge Base

A bilingual (English/Kiswahili) reference library for Grace, an AI assistant supporting participants in a general Roman Catholic prayer fellowship.

## Purpose
This repository contains reusable Catholic reference material for prayer, Scripture, Catholic teaching, liturgy, and fellowship activities. It is designed for ingestion by an n8n workflow and retrieval by an AI agent.

## Repository structure
- `00_COMMUNITY/`: fellowship identity and operating context
- `01_PRAYERS/`: common Catholic prayers and daily prayer guidance
- `02_DEVOTIONS/`: Rosary, Divine Mercy Chaplet, and other devotions
- `03_SCRIPTURE/`: Scripture reading and reflection guidance
- `04_CATHOLIC_FAITH/`: Catholic teaching, sacraments, and FAQs
- `05_LITURGY/`: liturgical year and Mass
- `06_COMMUNITY/`: meetings, activities, and fellowship conduct
- `07_LANGUAGE/`: English/Kiswahili response guidance

## Important local configuration
Before using this library in a real fellowship, update `00_COMMUNITY/community_overview.md` with the fellowship's approved name, parish/diocese, meeting schedule, contact person, and safeguarding/escalation contacts. Do not invent these details.

## Source and accuracy policy
1. The Bible translation used for public readings must be the translation approved or customarily used by the local parish/diocese.
2. Use the current Roman Missal, Liturgy of the Hours, approved prayer books, and diocesan/parish guidance for official liturgical texts.
3. Use the Catechism of the Catholic Church and the Holy See for doctrinal reference.
4. The Kiswahili wording in this starter library is explanatory unless explicitly identified as an approved liturgical text. Confirm exact wording with the local parish/diocese before public or liturgical use.
5. Grace must not invent Church teaching, sacramental permissions, dates of solemnities, or local parish announcements. When uncertain, say so and direct the participant to a priest or parish office.

## Suggested n8n ingestion
1. Retrieve Markdown files from GitHub.
2. Convert each file to text and split into appropriately sized chunks, retaining the file path as metadata.
3. Create embeddings using the selected embedding model.
4. Store chunks in a vector database.
5. Connect the vector store retriever to Grace's AI Agent.
6. Re-index when files change. Keep live fellowship information (current intentions, attendance, announcements, and meeting changes) in a separate controlled data source rather than treating it as permanent doctrine.

## Suggested metadata
`document_id`, `title`, `category`, `language`, `source_or_authority`, `review_status`, `last_reviewed`, `file_path`.

## Review status
This is a starter knowledge base, not an official publication of the Catholic Church. Have a knowledgeable parish catechist, priest, or other authorized reviewer check local adaptations and translations before deployment.
