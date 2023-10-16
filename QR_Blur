import cv2
import qrcode

# Function to generate a QR code
def generate_qr_code(data, filename):
    qr = qrcode.QRCode(
        version=1,
        error_correction=qrcode.constants.ERROR_CORRECT_L,
        box_size=10,
        border=4,
    )
    qr.add_data(data)
    qr.make(fit=True)
    
    img = qr.make_image(fill_color="black", back_color="white")
    img.save(filename)

# Function to apply a blur effect to an image
def apply_blur_to_image(input_image, output_image, blur_radius):
    image = cv2.imread(input_image)
    blurred_image = cv2.GaussianBlur(image, (blur_radius, blur_radius), 0)
    cv2.imwrite(output_image, blurred_image)

# Input data for the QR code
data = "https://www.example.com"

# Generate the QR code
qr_code_filename = "qr_code.png"
generate_qr_code(data, qr_code_filename)

# Apply a blur effect to the QR code
blurred_qr_code_filename = "blurred_qr_code.png"
blur_radius = 15  # Adjust this value for the desired blur effect
apply_blur_to_image(qr_code_filename, blurred_qr_code_filename, blur_radius)

print("QR code with blur effect created and saved as 'blurred_qr_code.png'")
