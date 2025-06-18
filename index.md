<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BulbiCAM - Neuro-Ophthalmic Biomarker Solution</title>
    <style>
        :root {
            --primary: #0066cc;
            --secondary: #004d99;
            --light: #f0f7ff;
        }
        * {
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        body {
            background-color: #f8f9fa;
            margin: 0;
            padding: 20px;
            color: #333;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0,0,0,0.1);
            overflow: hidden;
        }
        .header {
            background: var(--primary);
            color: white;
            padding: 20px;
            text-align: center;
        }
        .header h1 {
            margin: 0;
            font-size: 24px;
        }
        .header p {
            opacity: 0.9;
            margin: 5px 0 0;
        }
        .content {
            padding: 25px;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }
        .required:after {
            content: " *";
            color: #e32;
        }
        input, select, textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
        }
        .checkbox-group {
            margin: 15px 0;
            display: flex;
            align-items: center;
        }
        .checkbox-group input {
            width: auto;
            margin-right: 10px;
        }
        .qr-container {
            text-align: center;
            margin: 25px 0;
            padding: 15px;
            background: var(--light);
            border-radius: 8px;
        }
        .qr-code {
            width: 180px;
            height: 180px;
            margin: 0 auto;
            background: #fff;
            padding: 10px;
            border-radius: 4px;
        }
        button {
            background: var(--secondary);
            color: white;
            border: none;
            padding: 15px 25px;
            width: 100%;
            font-size: 18px;
            border-radius: 4px;
            cursor: pointer;
            transition: background 0.3s;
        }
        button:hover {
            background: #003d7a;
        }
        .footer {
            text-align: center;
            padding: 15px;
            font-size: 12px;
            color: #777;
            background: #f9f9f9;
        }
        @media (min-width: 768px) {
            .columns {
                display: flex;
                gap: 20px;
            }
            .column {
                flex: 1;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>BulbiCAM Interest Form</h1>
            <p>Revolutionizing Biomarker-Driven Healthcare</p>
        </div>
        
        <div class="content">
            <div class="qr-container">
                <h3>Scan to save this form</h3>
                <div class="qr-code">
                    <!-- QR code will be dynamically generated -->
                </div>
                <p>Take a photo to complete later</p>
            </div>
            
            <form id="bulbicamForm">
                <div class="columns">
                    <div class="column">
                        <div class="form-group">
                            <label class="required">Full Name</label>
                            <input type="text" required placeholder="Dr. First Last">
                        </div>
                    </div>
                    <div class="column">
                        <div class="form-group">
                            <label class="required">Email</label>
                            <input type="email" required placeholder="professional@institution.com">
                        </div>
                    </div>
                </div>
                
                <div class="form-group">
                    <label>Institution/Organization</label>
                    <input type="text" placeholder="Hospital, University, or Company">
                </div>
                
                <div class="form-group">
                    <label>Your Role</label>
                    <select>
                        <option value="">Select your role...</option>
                        <option>Neurologist</option>
                        <option>Ophthalmologist</option>
                        <option>Clinical Researcher</option>
                        <option>Pharma/Biotech R&D</option>
                        <option>Academic Researcher</option>
                        <option>Healthcare Administrator</option>
                        <option>Other</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label class="required">I'm interested in</label>
                    <div class="checkbox-group">
                        <input type="checkbox" id="neurodegenerative">
                        <label for="neurodegenerative">Neurodegenerative biomarkers (Parkinson's, Alzheimer's, MS)</label>
                    </div>
                    <div class="checkbox-group">
                        <input type="checkbox" id="ocular">
                        <label for="ocular">Ocular disease biomarkers (Glaucoma)</label>
                    </div>
                    <div class="checkbox-group">
                        <input type="checkbox" id="clinical">
                        <label for="clinical">Clinical implementation</label>
                    </div>
                    <div class="checkbox-group">
                        <input type="checkbox" id="trials">
                        <label for="trials">Drug trial applications</label>
                    </div>
                    <div class="checkbox-group">
                        <input type="checkbox" id="demo">
                        <label for="demo">Schedule a live demo</label>
                    </div>
                </div>
                
                <div class="form-group">
                    <label>How can we help?</label>
                    <textarea placeholder="Specific questions, materials requests, or timeline for adoption" rows="3"></textarea>
                </div>
                
                <button type="submit">Get BulbiCAM Information</button>
            </form>
        </div>
        
        <div class="footer">
            <p>BulbiCAM™ | Revolutionizing Neuro-Ophthalmic Biomarker Detection</p>
            <p>EUNOS Booth # | Follow us: @BulbiCAM</p>
        </div>
    </div>

    <script>
        // Generate QR code dynamically
        document.addEventListener('DOMContentLoaded', function() {
            const qrContainer = document.querySelector('.qr-code');
            const currentUrl = window.location.href;
            qrContainer.innerHTML = `<img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=${encodeURIComponent(currentUrl)}" alt="QR Code">`;
            
            // Form submission handler
            document.getElementById('bulbicamForm').addEventListener('submit', function(e) {
                e.preventDefault();
                alert('Thank you for your interest in BulbiCAM! We will contact you shortly with the requested information.');
                this.reset();
            });
        });
    </script>
</body>
</html>
