# Cross-camera-player-mapping

Project: Player Re-Identification using YOLO + ResNet18

✅ Objective

To match and track individual football players from two different video feeds using detection and visual appearance.

🧠 Approach and Methodology

Detection:

A pre-trained YOLOv11 model was used to detect players from each video frame.

Only class ID 0 (player) was considered from detections.

Cropping & Preprocessing:

Bounding boxes around detected players were cropped.

Resized and normalized using standard ImageNet values.

Feature Extraction:

A ResNet18 model (without the final FC layer) was used.

Each player crop was converted into a 512-dimensional feature vector.

Re-identification:

Cosine similarity between feature vectors from both video feeds.

Hungarian algorithm was used to solve the optimal matching.

⚙️ Set up and run the code

Install dependencies:
pip install -r requirements.txt

🧪 Techniques Tried

ResNet18-based appearance embeddings.

YOLO-based bounding box detection.

Linear sum assignment (Hungarian algorithm) for best-match mapping.

⚠️ Challenges Faced

Detection accuracy: Minor misses or false positives during crowded scenes.

Frame mismatch: No temporal consistency; mappings are made based only on appearance in individual frames.

Feature noise: Lighting differences between camera views affect feature stability.

⌛ Future Scope

YOLOv8: Replace the current YOLO model with an officially supported YOLOv8 model for better inference and ecosystem support.

🔍 Summary

The project successfully demonstrates a prototype system for player re-identification using computer vision, with room for significant improvements in detection robustness and identity consistency over time.
