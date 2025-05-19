# Flask GitHub Pages Website

This is a simple Flask application that can be hosted on GitHub Pages.

## Local Development

1. Clone this repository
2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Run the application:
   ```bash
   python app.py
   ```
5. Visit `http://localhost:5000` in your browser

## Deployment

This repository is set up to automatically deploy to GitHub Pages using GitHub Actions. The workflow will:

1. Build the Flask application
2. Deploy it to GitHub Pages
3. Make it available at `https://<your-username>.github.io/<repository-name>`

## Project Structure

- `app.py`: Main Flask application
- `templates/`: Contains HTML templates
- `requirements.txt`: Python dependencies
- `.github/workflows/`: GitHub Actions workflow files

## Customization

To customize the website:

1. Modify the HTML template in `templates/index.html`
2. Add new routes in `app.py`
3. Add new templates in the `templates/` directory 