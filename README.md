This project is a web application for scraping data from the website https://desktop.bg/computers-all
Used technologies: **Flask**, **SQLite**, **Scrapy**
                   
Content
- Installation💻
- Usage🚀
- Database Schema📋
- API Endpoints📡

## Installation ##💻

1. Clone the repository:

   - git clone https://github.com/kristiqnnikolov/desktop_scraper.git

   - cd desktop_scraper

2. Create a virtual environment:

    - python -m venv venv

3. Activate the virtual environment:

    - On Windows:
      venv\Scripts\activate

    - On macOS and Linux:
      source venv/bin/activate

4. Install the dependencies:

    - pip install -r requirements.txt
   
    - pip install flask (if you haven't already)

## Usage ## 🚀

1. Run the **Scrapy** spider to scrape data:

    - scrapy crawl get_computers_data -O computers_data.json

2. Initialize the database:

    - python 2_init_db.py

3. Insert scraped data into the database:

    - python 3_insert_data_to_db.py

4. Run the **Flask** application:

    - python 4_flask_app.py
   
6. Access the application:

   Open your web browser and go to `http://127.0.0.1:5000/computers`
   
   Apply **Pretty-print** check (for verifing bulgarian to english)

7. Verify data by running 5_verify_data.py (Optional).
   This file will print the total entries in the database.

   
## Database Schema ##📋

The database contains a single table `computers` with the following schema:

- `id` (INTEGER): Primary key, autoincrement.
- `cpu_name` (TEXT): Name of the CPU.
- `processor` (TEXT): Processor type.
- `motherboard` (TEXT): Motherboard type.
- `gpu` (TEXT): GPU type.
- `ram` (TEXT): RAM type.

## API Endpoints - GET /computers ##📡

Retrieve a list of computers with optional filtering.

**Parameters:**

- `processor` (optional): Filter by processor type.
- `gpu` (optional): Filter by GPU type.
- `motherboard` (optional): Filter by motherboard type.
- `ram` (optional): Filter by RAM type.

**Example Request:**

curl "http://127.0.0.1:5000/computers?processor=Intel&gpu=NVIDIA"







