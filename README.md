# Instructions

git clone https://github.com/microsoft/fara
cd fara
python -m venv .venv
.\.venv\Scripts\activate
pip install -e .
playwright install

Dans un autre terminal :
ollama pull huihui_ai/fara-abliterated:7b
ollama run huihui_ai/fara-abliterated:7b

Dans un autre terminal :

python -m http.server 8000

Puis, dans un autre terminal :

fara-cli --task "Remplis le formulaire avec les informations à disposition. NOM = 'Jean DUPONT' DATE_OF_BIRTH = '05/05/1995' MAIL = 'jean@du.pont' ADDRESS = '5 rue du Général 75002 Paris' USERNAME = 'jean' PASSWORD = 'pass' " `  --endpoint_config endpoint_configs/ollama_config.json --headful --start_page http://localhost:8000/