THIS REPOSTIORY WAS CREATED WHILE LEARNING THE RASA FRAMEWORK.

These are the steps that I followed.

1.
    installed Python 3.9.0

    created virtual environment using:
        python -m venv ./venv

    ran commands:
        venv\Scripts\activate
        pip install rasa
        rasa init

2.
    in data/nlu.yml, 
        added 
            - intent: weather
            examples: |
                - how is the weather today ?
                - what is the weather
                - tell me the weather
                - weather

    in data/stories.yml,
        added
            - story: tell weather
            steps:
            - intent: weather
            - action: utter_weather

    in /domain.yml,
        added
            utter_weather:
            - text: "The weather is great today!

    in /domain.yml,
        added under
            intents:
                weather

    ran commands:
        rasa train
        rasa shell