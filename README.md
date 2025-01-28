## Jayce - AI Voice Assistant

Jayce is an AI Voice Assistant that leverages multiple technologies and services to provide a seamless voice interaction experience. Below are the main components and setup instructions for the project.

[Try Jayce](https://jayce-fe.vercel.app/)

### Components

1. **LiveKit WebRTC Server**: Handles voice communication between the user and the AI model using the LiveKit SDK to establish a WebRTC connection. Deployed on a Google Cloud VM instance.
2. **Custom Voice Agent Backend**: Manages voice communication and uses OpenAI's ChatGPT model to generate responses. Deployed in Python on Google Cloud VM instance.
3. **Next.js Frontend**: Provides the web interface for user interaction, built with Next.js and LiveKit's library to communicate with the backend service. Deployed on Vercel.

## Development

### Prerequisites

Ensure you have the necessary prerequisites installed as per the [LiveKit documentation](https://docs.livekit.io/agents/quickstarts/voice-agent/#prerequisites).

### Backend (Python) Setup Instructions

1. **Create a virtual environment**:
    ```sh
    python -m venv venv
    ```

2. **Activate the virtual environment**:
    - On Windows:
        ```sh
        venv\Scripts\Activate.ps1
        ```
    - On Unix or MacOS:
        ```sh
        source venv/bin/activate
        ```

3. **Install the required dependencies**:
    ```sh
    python -m pip install -r requirements.txt
    ```

4. **Run the development server**:
    ```sh
    python agent.py dev
    ```

### Frontend (Next.js) Setup Instructions

1. **Install the required dependencies**:
    ```sh
    npm install
    ```

2. **Run the development server**:
    ```sh
    npm run dev
    ```

### Deployment

#### LiveKit Server

Deployed on a Google Cloud VM instance. Follow the steps in this [guide](https://medium.com/@kesaralive/hosting-livekit-server-on-google-cloud-a-step-by-step-guide-52c5b3746a3e).

#### Custom Voice Agent Backend

1. Create a Google Cloud VM instance.
2. Upload `agent.py`, `requirements.txt`, and `.env.local` files.
3. Run the Python script with `nohup` to keep it running after closing the SSH terminal:
    ```sh
    nohup python3 agent.py prod &
    ```

#### Assistant Frontend

Deployed on Vercel at [https://jayce-fe.vercel.app/](https://jayce-fe.vercel.app/). To deploy your own instance, follow the [Vercel deployment guide](https://nextjs.org/docs/deployment) or run the following command:

```sh
npx vercel
```

### Costs

- ChatGPT API credits
- Domain purchase (intact.website)
- Two Google Cloud VM instances for hosting the LiveKit server and Custom Voice Agent Backend

### Challenges

- **LiveKit Server**: Setting up a deployed LiveKit server and establishing a WebRTC connection was challenging due to the lack of detailed documentation, especially for each type of cloud service provider.
- **Voice Agent Backend**: Integrating the ChatGPT model API only worked when paying for credits, and no free deployment service was seamless enough to host the LiveKit Server and the Voice Agent Backend.
- **Time Constraints**: The project is meant to be completed in a short time frame, which made it a challenge to fully explore configurations with multiple cloud options and service providers, customize the assistant's responses, integrate more external features and APIs, or create a more polished user interface.