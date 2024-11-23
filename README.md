# SightPay
**SightPay**: Assisting visually impaired individuals with financial transactions using AI.

**SightPay** is an AI-powered solution designed to assist visually impaired individuals with financial transactions by utilizing advanced computer vision and natural language processing technologies.

## Features
- **Currency Detection**: Detects various denominations of Egyptian currency (e.g., 5, 10, 10(New), 20, 20(New), 50, 100, and 200 EGP) using a camera.
- **Invoice Processing**: Extracts information from invoices, such as total amounts, item descriptions, unit prices, and quantities using AI-powered content generation.
- **Audio Feedback**: Provides feedback using text-to-speech for detected currency and invoice data.
- **Transaction Verification**: Confirms payment details using voice commands.
- **Integration with Gemini**: Uses Google’s Gemini model for additional data processing and content generation tasks.

## SightPay System

### Installation

1. **Clone the repository** to your local machine:
   ```bash
   git clone https://github.com/gihankhalil1/SightPay.git
   ```
2. **Navigate to the project directory**
   ```bash
   cd SightPay
   ```
3. **Install required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
4. **Download the pre-trained currency detection model**:
(model_1.h5) and place it in the model/ directory.

## Usage 
## Running the SightPay System
1. **Launch the application**:
  ```bash
   python app.py
   ```
This will open a window showing the live video feed from your camera. The system will attempt to detect Egyptian currency and read the amount aloud using text-to-speech and voice-to-text.

2. **To process invoices**:

-Say "Capture the photo" to the system. This will capture an image of the invoice using the ---camera.
-The app will upload the image to Gemini for processing and extract details such as total amounts, item lists, and descriptions. Say any of them to be processed.
-If it is a currency image, the app will upload the image to the Currency Detection Model for detecting the label.
-SightPay will tell you what you want to know.

##Components
### Currency Detection Model
 This model is trained using a EfficientNetV2L to classify Egyptian currency into different denominations.

### Generative AI
The system uses **Google's Gemini model** to extract valuable data from invoices. It can process captured images of invoices and automatically extract details such as:
- Total amounts
- Item descriptions
- Item quantities
- Unit prices

 ### Voice Interaction
The application has integrated voice interaction for enhanced user experience. Users can interact with the system through voice commands, allowing them to:

-Trigger the currency detection system via voice commands.
-Receive spoken feedback about detected currency and invoice details.
  
This voice interaction is powered by **pyttsx3**, which provides text-to-speech functionality, enabling the app to read out detected currency denominations and invoice information aloud.

## GUI and Speech Feedback

The application features a **GUI** that displays the camera feed in real-time using `customtkinter`. This allows users to visually see the live feed from their camera and interact with the currency detection system seamlessly.

Additionally, **speech feedback** is provided using `pyttsx3`. The system announces detected currency denominations and invoice details aloud, enhancing the user experience by providing auditory feedback.

---

## Model Training

To train the currency detection model, follow these steps:

1. **Prepare the dataset** by labeling images of Egyptian currency denominations.
2. Use the provided code to **preprocess** the images and labels.
3. **Use the pretrained EfficientNetV2L model as Base model** using the preprocessed dataset.
4. **Save the trained model** as `model_1.h5` in the `model/` directory.

Example model training code:

```python
history = model.fit(train_images, train_labels_one_hot, epochs=num_epochs, batch_size=batch_size, validation_data=(valid_images, valid_labels_one_hot))


