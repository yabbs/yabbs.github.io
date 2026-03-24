# Data viewer specification

Deliver a fully self‑contained, single‑file interactive data viewer as part of the final analytic output.

This viewer must satisfy the following requirements:

## 1. Architecture & Deployment Requirements
The viewer must be delivered as one standalone .html file.

The file must run locally when opened via double‑click in a modern browser (Chrome or Edge).

The viewer must require no server, no installation, no command‑line tools, and no external dependencies.

All JavaScript, CSS, and data must be embedded inline within the HTML file.

The viewer must not rely on:

external CDNs

external script imports

external data files

fetch() or XHR requests

local servers or Python/Node runtimes

## 2. Data Handling Requirements
The viewer must support large datasets (tens of thousands of rows or more).

Data must be embedded using a compressed inline representation (e.g., base64‑encoded, gzipped, or LZ‑compressed JSON).

On load, the viewer must decompress the dataset in the browser and make it available to the visualization layer.

The viewer must not require the user to select or load files manually unless explicitly specified.

## 3. Interactivity & Filtering Requirements
The viewer must provide a client‑side UI that enables the user to:

Select subsets of the data via:

dropdown menus

checkboxes

sliders

or other appropriate controls

Apply multiple filters simultaneously

Update all charts and summary statistics immediately in response to filter changes

Reset filters to default state

Filtering must occur entirely in the browser, with no server calls.

## 4. Visualization Requirements
Visualizations must be implemented using D3.js (embedded inline).

The viewer must include:

at least one primary chart (e.g., scatterplot, bar chart, line chart)

optional summary statistics (mean, standard deviation, counts, etc.)

dynamic updates when filters change

Charts must render without external libraries or frameworks beyond D3.

## 5. Performance Requirements
Filtering and chart updates must complete within 200 ms for datasets up to at least 50,000 rows.

The viewer must remain responsive during interaction.

All computation must occur client‑side using efficient JavaScript operations or lightweight in‑browser query engines.

## 6. Usability Requirements
The viewer must open and function correctly when the user double‑clicks the HTML file.

No technical knowledge (e.g., running servers, installing Python, using command‑line tools) shall be required.

The UI must be intuitive and require no training.

## 7. Security & Compliance Requirements
The viewer must not transmit data outside the user’s machine.

All logic must execute locally in the browser.

No external network requests of any kind are permitted.

## 8. Deliverables
A single .html file meeting all requirements above.

Brief inline documentation (commented in the HTML) describing:

data embedding method

filtering logic

chart update mechanism