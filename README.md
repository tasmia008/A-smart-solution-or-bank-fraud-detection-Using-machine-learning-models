<!DOCTYPE html>

  <h1>🛡️ Smart Solution for Bank Fraud Detection Using Machine Learning</h1>
  <p>This project addresses the critical issue of bank fraud by implementing machine learning techniques on a highly imbalanced dataset. The focus lies in detecting fraudulent financial transactions with improved accuracy, precision, and recall by leveraging various data balancing strategies and robust model evaluation.</p>

 <h2>📊 Dataset</h2>
  <p>The benchmark dataset used contains 1 million transactions with 31 features. Among them, only 11,029 transactions are labeled as fraudulent (<code>device_fraud_count = True</code>), making the dataset highly imbalanced.</p>

  <h2>❌ Performance Before Using the Balancing Dataset</h2>
  <p>Initial experiments using <strong>PyCaret</strong>, a low-code ML library, showed:</p>
  <table border="1" cellpadding="5">
    <tr>
      <th>Model</th>
      <th>Accuracy</th>
      <th>Precision</th>
      <th>Recall</th>
      <th>F1 Score</th>
      <th>AUC</th>
    </tr>
    <tr><td>RandomForest</td><td>1.0</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr>
    <tr><td>AdaBoost</td><td>1.0</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr>
    <tr><td>GradientBoosting</td><td>1.0</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr>
    <tr><td>XGBoost</td><td>1.0</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr>
    <tr><td>CatBoost</td><td>1.0</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr>
    <tr><td>LightGBM</td><td>1.0</td><td>0.0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr>
  </table>
  <p>Despite perfect accuracy, the models failed in detecting fraud due to the imbalanced dataset.</p>

  <h2>✅ Performance After Using a Balancing Dataset</h2>
  <p>Balancing techniques like <strong>SMOTE</strong>, <strong>ADASYN</strong>, <strong>SMOTETomek</strong>, and <strong>undersampling</strong> were applied. Here's a sample summary:</p>
  <table border="1" cellpadding="5">
    <tr>
      <th>Model</th>
      <th>Sampling</th>
      <th>Accuracy</th>
      <th>Precision</th>
      <th>Recall</th>
      <th>F1 Score</th>
      <th>AUC</th>
    </tr>
    <tr><td>RandomForest</td><td>ADASYN</td><td>0.9872</td><td>0.1904</td><td>0.0586</td><td>0.0893</td><td>0.8199</td></tr>
    <tr><td>AdaBoost</td><td>ADASYN</td><td>0.9226</td><td>0.0671</td><td>0.4802</td><td>0.1177</td><td>0.8334</td></tr>
    <tr><td>XGBoost</td><td>SMOTE</td><td>0.9712</td><td>0.1229</td><td>0.2751</td><td>0.1698</td><td>0.8462</td></tr>
    <tr><td>CatBoost</td><td>SMOTE</td><td>0.9891</td><td>0.3862</td><td>0.0372</td><td>0.0678</td><td>0.8511</td></tr>
    <tr><td>LightGBM</td><td>SMOTE</td><td>0.9883</td><td>0.2976</td><td>0.0682</td><td>0.1108</td><td>0.8527</td></tr>
    <tr><td>AdaBoost</td><td>Under</td><td>0.7990</td><td>0.0397</td><td>0.7672</td><td>0.0755</td><td>0.8507</td></tr>
  </table>
  <p>These results show improved recall and F1 scores, indicating better fraud detection performance, although accuracy decreased slightly.</p>

  <h2>🧠 Comparison with Contemporary AI Research</h2>
  <ul>
    <li><strong>Lightweight and fast:</strong> This project uses traditional ML models, which are less computationally intensive than deep learning alternatives.</li>
    <li><strong>Versatile sampling techniques:</strong> Various methods like SMOTE, ADASYN, and undersampling were compared.</li>
    <li><strong>Robust evaluation:</strong> Stratified K-Fold Cross-Validation was used to preserve class distribution.</li>
  </ul>

</body>
</html>
