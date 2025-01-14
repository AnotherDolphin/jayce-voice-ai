## How to use

1. Make sure to install the LiveKit [prerequisites](https://docs.livekit.io/agents/quickstarts/voice-agent/#prerequisites)(https://docs.livekit.io/agents/quickstarts/voice-agent/#prerequisites)

## Backend (Python) Setup Instructions

1. Create a virtual environment:
    ```sh
    python -m venv venv
    ```

2. Activate the virtual environment:
    - On Windows:
        ```sh
        venv\Scripts\Activate.ps1
        ```
    - On Unix or MacOS:
        ```sh
        source venv/bin/activate
        ```

3. Install the required dependencies:
    ```sh
    python -m pip install -r requirements.txt
    ```

4. Run the development server:
    ```sh
    python agent.py dev
    ```

## Frontend (Next.js) Setup Instructions

1. Install the required dependencies:
    ```sh
    npm install
    ```

2. Run the development server:
    ```sh
    npm run dev
    ```

docker build -t jayce-voice-ai .

docker run -d --name jayce-voice-ai --env-file .env.local -p 8080:8080 jayce-voice-ai