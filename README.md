<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DR.PERFECT - Virtual Medical Consultations</title>
<script src="https://cdn.tailwindcss.com"></script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
<link href="https://cdn.jsdelivr.net/npm/remixicon@4.5.0/fonts/remixicon.css" rel="stylesheet">
<script>
tailwind.config = {
darkMode: 'class',
theme: {
extend: {
colors: {
primary: '#0284c7',
secondary: '#64748b'
},
borderRadius: {
'none': '0px',
'sm': '4px',
DEFAULT: '8px',
'md': '12px',
'lg': '16px',
'xl': '20px',
'2xl': '24px',
'3xl': '32px',
'full': '9999px',
'button': '8px'
}
}
}
}
</script>
<style>
:where([class^="ri-"])::before { content: "\f3c2"; }
@keyframes float {
0% { transform: translateY(0px) rotate(0deg); }
50% { transform: translateY(-20px) rotate(2deg); }
100% { transform: translateY(0px) rotate(0deg); }
}
@keyframes gradientBG {
0% { background-position: 0% 50%; }
50% { background-position: 100% 50%; }
100% { background-position: 0% 50%; }
}
.parallax-bg {
background-attachment: fixed;
background-position: center;
background-repeat: no-repeat;
background-size: cover;
position: relative;
}
.gradient-bg {
background: linear-gradient(-45deg, #0284c7, #0ea5e9, #38bdf8, #7dd3fc);
background-size: 400% 400%;
animation: gradientBG 15s ease infinite;
}
.glass-effect {
backdrop-filter: blur(10px);
background: rgba(255, 255, 255, 0.1);
border: 1px solid rgba(255, 255, 255, 0.2);
}
.parallax-content {
transform: translateZ(0);
will-change: transform;
}
.floating-element {
animation: float 6s ease-in-out infinite;
}
@keyframes pulse {
0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(2, 132, 199, 0.4); }
70% { transform: scale(1.05); box-shadow: 0 0 0 10px rgba(2, 132, 199, 0); }
100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(2, 132, 199, 0); }
}
@keyframes tilt {
0% { transform: perspective(1000px) rotateY(0deg); }
100% { transform: perspective(1000px) rotateY(360deg); }
}
.testimonial-card {
transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
transform-style: preserve-3d;
perspective: 1000px;
}
.testimonial-card:hover {
transform: translateY(-10px) rotateX(10deg) rotateY(10deg);
box-shadow: 20px 20px 60px rgba(0,0,0,0.1), -20px -20px 60px rgba(255,255,255,0.8);
}
.specialty-card {
transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
animation: float 6s ease-in-out infinite;
transform-style: preserve-3d;
perspective: 1000px;
}
.specialty-card:hover {
transform: translateY(-15px) scale(1.05) rotateX(10deg) rotateY(10deg);
box-shadow: 20px 20px 60px rgba(0,0,0,0.1), -20px -20px 60px rgba(255,255,255,0.8);
}
.specialty-card:hover i {
transform: translateZ(20px) rotate(360deg);
transition: all 0.5s ease;
}
.specialty-card:hover i {
animation: pulse 2s infinite;
}
.chat-widget {
transition: all 0.3s ease;
animation: pulse 2s infinite;
}
.chat-widget:hover {
transform: scale(1.1) rotate(5deg);
}
.hero-image {
animation: float 6s ease-in-out infinite;
transform-style: preserve-3d;
perspective: 1000px;
position: relative;
}
.hero-image:hover {
animation-play-state: paused;
transform: translateZ(50px) rotateY(10deg);
transition: all 0.5s ease;
}
.hero-image::after {
content: '';
position: absolute;
inset: 0;
background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
animation: shimmer 2s infinite;
pointer-events: none;
}
@keyframes shimmer {
0% { transform: translateX(-100%) rotate(45deg); }
100% { transform: translateX(100%) rotate(45deg); }
}
.featured-doctor-card {
transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
transform-style: preserve-3d;
perspective: 1000px;
}
.featured-doctor-card:hover {
transform: translateZ(30px) rotateX(10deg) rotateY(5deg);
box-shadow: 30px 30px 60px rgba(0,0,0,0.1), -30px -30px 60px rgba(255,255,255,0.8);
}
.featured-doctor-card:hover img {
transform: translateZ(40px) scale(1.1) rotate(5deg);
transition: all 0.5s ease;
}
.featured-doctor-card:hover .text-center {
transform: translateZ(20px);
transition: all 0.5s ease;
}
.featured-doctor-card img {
transition: all 0.5s ease;
}
.featured-doctor-card:hover img {
transform: scale(1.1) rotate(5deg);
}
.stats-card {
transition: all 0.3s ease;
transform-style: preserve-3d;
perspective: 1000px;
position: relative;
}
.stats-card:hover {
transform: translateZ(30px) rotateX(10deg) rotateY(5deg);
box-shadow: 20px 20px 60px rgba(0,0,0,0.1), -20px -20px 60px rgba(255,255,255,0.8);
}
.stats-card:hover i {
transform: translateZ(20px) rotateY(360deg);
transition: all 0.8s ease;
}
.stats-card:hover::after {
content: '';
position: absolute;
inset: 0;
background: linear-gradient(125deg, transparent 0%, rgba(255,255,255,0.2) 50%, transparent 100%);
animation: lightPass 2s infinite;
}
@keyframes lightPass {
0% { transform: translateX(-100%); }
100% { transform: translateX(100%); }
}
.stats-card i {
transition: all 0.3s ease;
}
.stats-card:hover i {
transform: rotateY(360deg);
}
.modal-content {
animation: modalSlideIn 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}
@keyframes modalSlideIn {
from { transform: translateY(-100px); opacity: 0; }
to { transform: translateY(0); opacity: 1; }
}
.button-3d {
transition: all 0.3s ease;
transform-style: preserve-3d;
transform: translateZ(0);
perspective: 1000px;
position: relative;
overflow: hidden;
}
.button-3d:hover {
transform: translateZ(20px) scale(1.05) rotateX(10deg);
box-shadow: 0 15px 30px rgba(0,0,0,0.15);
}
.button-3d:hover::before {
content: '';
position: absolute;
top: -50%;
left: -50%;
width: 200%;
height: 200%;
background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
transform: rotate(45deg);
animation: shine 1.5s infinite;
}
@keyframes shine {
0% { transform: translateX(-100%) rotate(45deg); }
100% { transform: translateX(100%) rotate(45deg); }
}
.button-3d:active {
transform: translateZ(10px) scale(0.95);
}
</style>
</head>
<body class="bg-white dark:bg-gray-900">
<nav class="fixed top-0 w-full bg-gradient-to-r from-white via-gray-50 to-white dark:from-gray-900 dark:via-gray-800 dark:to-gray-900 shadow-sm z-50">
<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
<div class="flex justify-between h-16">
<div class="flex items-center">
<h1 class="text-3xl font-['Playfair_Display'] font-black text-primary dark:text-white">DR.PERFECT</h1>
</div>
<div class="hidden md:flex items-center space-x-8">
<a href="" class="text-gray-700 dark:text-gray-300 hover:text-primary dark:hover:text-white">Home</a>
<a href="#about" class="text-gray-700 dark:text-gray-300 hover:text-primary dark:hover:text-white">About Us</a>
<a href="#specialties" class="text-gray-700 dark:text-gray-300 hover:text-primary dark:hover:text-white">Specialties</a>
<a href="#featured-doctors" class="text-gray-700 dark:text-gray-300 hover:text-primary dark:hover:text-white">Doctors</a>
<a href="#contact" class="text-gray-700 dark:text-gray-300 hover:text-primary dark:hover:text-white">Contact</a>
<button id="themeToggle" class="p-2 rounded-full hover:bg-gray-100 dark:hover:bg-gray-700" aria-label="Toggle theme">
<i class="ri-sun-line text-xl text-gray-700 dark:text-gray-300 dark:hidden"></i>
<i class="ri-moon-line text-xl text-gray-700 dark:text-gray-300 hidden dark:block"></i>
</button>
<button onclick="openSignInModal()" class="px-4 py-2 text-sm font-medium text-gray-700 hover:text-primary !rounded-button button-3d transition-transform active:scale-95">Sign In</button>
<div id="signInModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
<div class="bg-white rounded-lg p-8 w-96 relative modal-content">
<button onclick="closeSignInModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<h2 class="text-2xl font-semibold mb-6">Sign In</h2>
<form id="signInForm" class="space-y-4">
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Email</label>
<input type="email" id="signInEmail" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Password</label>
<input type="password" id="signInPassword" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" required>
</div>
<div class="flex items-center justify-between">
<div class="flex items-center">
<input type="checkbox" id="remember" class="h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded">
<label for="remember" class="ml-2 block text-sm text-gray-700">Remember me</label>
</div>
<a href="#" class="text-sm text-primary hover:text-primary/90">Forgot password?</a>
</div>
<button type="submit" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">Sign In</button>
</form>
<div class="mt-4 text-center">
<p class="text-sm text-gray-600">Don't have an account? <a href="#" class="text-primary hover:text-primary/90">Register</a></p>
</div>
</div>
</div>
<button onclick="openRegisterModal()" class="px-4 py-2 text-sm font-medium text-white bg-primary hover:bg-primary/90 !rounded-button transition-transform active:scale-95 hover:shadow-lg">Register</button>
<div id="registerModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
<div class="bg-white rounded-lg p-8 w-[600px] max-h-[90vh] overflow-y-auto relative">
<button onclick="closeRegisterModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<h2 class="text-2xl font-semibold mb-6">Create Account</h2>
<form id="registerForm" class="space-y-4 overflow-y-auto pr-2">
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Full Name</label>
<input type="text" id="registerName" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Email</label>
<input type="email" id="registerEmail" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Password</label>
<input type="password" id="registerPassword" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Confirm Password</label>
<input type="password" id="confirmPassword" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">User Type</label>
<select id="userType" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" required>
<option value="">Select user type</option>
<option value="doctor">Doctor</option>
<option value="patient">Patient</option>
</select>
</div>
<div id="doctorFields" class="hidden space-y-4 mt-4">
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Medical License Number</label>
<input type="text" id="licenseNumber" pattern="[A-Z0-9]{8,}" title="License number must be at least 8 characters long and contain only uppercase letters and numbers" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" placeholder="e.g. MED123456">
<p class="text-xs text-gray-500 mt-1">Format: Minimum 8 characters, uppercase letters and numbers only</p>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Specialty</label>
<select id="specialty" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary">
<option value="">Select specialty</option>
<option value="cardiology">Cardiology</option>
<option value="neurology">Neurology</option>
<option value="psychiatry">Psychiatry</option>
<option value="pulmonology">Pulmonology</option>
<option value="dermatology">Dermatology</option>
<option value="endocrinology">Endocrinology</option>
<option value="gastroenterology">Gastroenterology</option>
<option value="oncology">Oncology</option>
<option value="pediatrics">Pediatrics</option>
<option value="rheumatology">Rheumatology</option>
</select>
</div>
<div class="mt-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Years of Experience</label>
<input type="number" id="experience" min="1" max="50" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" required>
</div>
<div class="mt-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Board Certification</label>
<input type="text" id="certification" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" placeholder="e.g. American Board of Internal Medicine" required>
</div>
</div>
<div class="flex items-center">
<input type="checkbox" id="terms" class="h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded" required>
<label for="terms" class="ml-2 block text-sm text-gray-700">I agree to the <a href="#" class="text-primary hover:text-primary/90">Terms and Conditions</a></label>
</div>
<button type="submit" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">Create Account</button>
</form>
<div class="mt-4 text-center">
<p class="text-sm text-gray-600">Already have an account? <a href="#" onclick="switchToSignIn()" class="text-primary hover:text-primary/90">Sign In</a></p>
</div>
</div>
</div>
</div>
</div>
</div>
</nav>
<main class="pt-16">
<section class="relative h-[600px] bg-cover bg-center parallax-bg" style="background-image: url('https://public.readdy.ai/ai/img_res/dbe3387dde5f00ea8f858cebf0243e8e.jpg')">
<div class="absolute inset-0 bg-black/40"></div>
<div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-full flex items-center">
<div class="max-w-2xl">
<h1 class="text-5xl font-['Playfair_Display'] font-bold text-white mb-6">Connect with Patients Worldwide Through Virtual Care</h1>
<p class="text-xl text-white mb-8">Join thousands of healthcare professionals providing expert care through secure video consultations. Expand your practice globally while maintaining work-life balance.</p>
<div class="flex space-x-4">
<button onclick="openDoctorRegistration()" class="px-8 py-4 text-lg font-medium text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:-translate-y-1 hover:shadow-xl active:translate-y-0 active:shadow-md">Join as a Doctor</button>
<button onclick="openLearnMoreModal()" class="px-8 py-4 text-lg font-medium text-white border-2 border-white hover:bg-white hover:text-gray-900 !rounded-button transition-all duration-300 transform hover:scale-105 active:scale-100 hover:shadow-lg">Learn More</button>
</div>
</div>
</div>
</div>
</section>
<section id="body-visualizer" class="py-20 bg-gradient-to-br from-sky-50 via-indigo-50 to-emerald-50">
<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
<div class="text-center mb-12">
<h2 class="text-4xl font-['Playfair_Display'] font-bold text-gray-900 mb-4">Interactive Body Visualizer</h2>
<p class="text-xl text-gray-600">Click on any body part to learn more about symptoms and treatments</p>
</div>
<div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
<div class="relative">
<img src="https://readdy.ai/api/search-image?query=anatomical illustration of human body with transparent layers showing muscles, bones and organs, medical textbook style, clean white background, professional medical illustration&width=600&height=800&seq=26&orientation=portrait" alt="Human Body" class="w-full h-auto" id="bodyImage">
<div class="absolute inset-0">
<div class="body-part" style="top: 10%; left: 50%; transform: translate(-50%, -50%);" onclick="showBodyPartInfo('head')">
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary"></div>
</div>
<div class="body-part" style="top: 25%; left: 50%; transform: translate(-50%, -50%);" onclick="showBodyPartInfo('chest')">
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary"></div>
</div>
<div class="body-part" style="top: 40%; left: 50%; transform: translate(-50%, -50%);" onclick="showBodyPartInfo('abdomen')">
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary"></div>
</div>
<div class="body-part" style="top: 60%; left: 30%; transform: translate(-50%, -50%);" onclick="showBodyPartInfo('arms')">
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary"></div>
</div>
<div class="body-part" style="top: 80%; left: 50%; transform: translate(-50%, -50%);" onclick="showBodyPartInfo('legs')">
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary"></div>
</div>
</div>
</div>
<div class="bg-white p-6 rounded-lg shadow-sm" id="bodyPartInfo">
<h3 class="text-2xl font-semibold mb-4">Select a Body Part</h3>
<p class="text-gray-600">Click on any highlighted point on the body to learn more about that area, including common conditions, symptoms, and available treatments.</p>
<div class="mt-6">
<button onclick="toggleNervousSystem()" class="px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">Toggle Nervous System View</button>
</div>
</div>
</div>
</div>
</section>
<section id="specialties" class="py-20 bg-gray-50">
<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
<div class="text-center mb-12">
<h2 class="text-4xl font-['Playfair_Display'] font-bold text-gray-900 mb-4">Medical Specialties</h2>
<p class="text-xl text-gray-600">Choose from a wide range of medical specialties</p>
</div>
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-6 gap-8">
<div onclick="openPharmacyModal()" class="specialty-card bg-white p-6 rounded-lg shadow-sm cursor-pointer">
<div class="w-12 h-12 flex items-center justify-center bg-primary/10 rounded-full mb-4">
<i class="ri-medicine-bottle-line text-primary text-2xl"></i>
</div>
<h3 class="text-xl font-semibold text-gray-900 mb-2">Online Pharmacy</h3>
<p class="text-gray-600">24/7 Medicine Delivery</p>
</div>
<div onclick="openHealthLeaveModal()" class="specialty-card bg-white p-6 rounded-lg shadow-sm cursor-pointer">
<div class="w-12 h-12 flex items-center justify-center bg-primary/10 rounded-full mb-4">
<i class="ri-file-text-line text-primary text-2xl"></i>
</div>
<h3 class="text-xl font-semibold text-gray-900 mb-2">Health Leave</h3>
<p class="text-gray-600">Online Medical Certificate</p>
</div>
<div onclick="openCardiologyModal()" class="specialty-card bg-white p-6 rounded-lg shadow-sm cursor-pointer">
<div class="w-12 h-12 flex items-center justify-center bg-primary/10 rounded-full mb-4">
<i class="ri-heart-pulse-line text-primary text-2xl"></i>
</div>
<h3 class="text-xl font-semibold text-gray-900 mb-2">Cardiology</h3>
<p class="text-gray-600">125 Specialists Available</p>
</div>
<div id="cardiologyModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
<div class="bg-white rounded-lg p-8 w-[1000px] max-h-[90vh] overflow-y-auto relative">
<button onclick="closeCardiologyModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<h2 class="text-3xl font-['Playfair_Display'] font-bold text-gray-900 mb-6">Cardiology Department</h2>
<div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mb-8">
<div class="col-span-2">
<div class="bg-gray-50 p-6 rounded-lg mb-6">
<h3 class="text-xl font-semibold mb-4">Available Services</h3>
<div class="grid grid-cols-2 gap-4">
<div class="flex items-start space-x-3">
<i class="ri-heart-pulse-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Cardiac Consultation</h4>
<p class="text-sm text-gray-600">Virtual consultation with cardiologists</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-file-list-3-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">ECG Review</h4>
<p class="text-sm text-gray-600">Expert analysis of ECG reports</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-heart-2-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Risk Assessment</h4>
<p class="text-sm text-gray-600">Cardiovascular risk evaluation</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-medicine-bottle-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Medication Review</h4>
<p class="text-sm text-gray-600">Comprehensive medication analysis</p>
</div>
</div>
</div>
</div>
<div class="bg-white border rounded-lg p-6">
<h3 class="text-xl font-semibold mb-4">Available Time Slots</h3>
<div class="grid grid-cols-2 gap-4">
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectTimeSlot('2025-03-07 09:00', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 09:00 AM</p>
<p class="text-sm text-gray-600 relative">Dr. Sarah Anderson</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectTimeSlot('2025-03-07 11:30', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 11:30 AM</p>
<p class="text-sm text-gray-600 relative">Dr. Michael Chen</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectTimeSlot('2025-03-07 14:00', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 02:00 PM</p>
<p class="text-sm text-gray-600 relative">Dr. James Wilson</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectTimeSlot('2025-03-07 16:30', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 04:30 PM</p>
<p class="text-sm text-gray-600 relative">Dr. Emily Rodriguez</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
</div>
</div>
</div>
<div class="bg-gray-50 p-6 rounded-lg">
<h3 class="text-xl font-semibold mb-4">Book Appointment</h3>
<form id="cardiologyForm" class="space-y-4">
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Full Name</label>
<input type="text" id="cardioName" class="w-full px-3 py-2 border border-gray-300 rounded-md" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Age</label>
<input type="number" id="cardioAge" class="w-full px-3 py-2 border border-gray-300 rounded-md" required min="1" max="120">
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Selected Time Slot</label>
<input type="text" id="cardioTimeSlot" class="w-full px-3 py-2 border border-gray-300 rounded-md bg-gray-100" readonly>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Reason for Visit</label>
<textarea id="cardioReason" class="w-full px-3 py-2 border border-gray-300 rounded-md" rows="3" required></textarea>
</div>
<button type="submit" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:-translate-y-1 hover:shadow-lg active:translate-y-0 active:shadow-md">Book Appointment</button>
</form>
</div>
</div>
<div class="border-t mt-8 pt-8">
<h3 class="text-xl font-semibold mb-4">Our Cardiologists</h3>
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/68d9b4a95bd97e7673718005c8aef6e6.jpg" alt="Dr. Sunita Gupta" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Sunita Gupta</h4>
<p class="text-sm text-center text-gray-600">Interventional Cardiologist</p>
<p class="text-xs text-center text-gray-500">MBBS, MD, DM (Cardiology)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.9 (120+ reviews)</span>
</div>
</div>
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/28f8a2913a68353018c78da4616f34b6.jpg" alt="Dr. Vikram Mehta" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Vikram Mehta</h4>
<p class="text-sm text-center text-gray-600">Clinical Cardiologist</p>
<p class="text-xs text-center text-gray-500">MBBS, DNB (Cardiology)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.8 (95+ reviews)</span>
</div>
</div>
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/4360dc06a84be3c7eb632168ba1449f5.jpg" alt="Dr. Rahul Verma" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Rahul Verma</h4>
<p class="text-sm text-center text-gray-600">Cardiac Electrophysiologist</p>
<p class="text-xs text-center text-gray-500">MBBS, MD, DM (Cardiology)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.9 (150+ reviews)</span>
</div>
</div>
</div>
</div>
</div>
</div>
<div onclick="openNeurologyModal()" class="specialty-card bg-white p-6 rounded-lg shadow-sm cursor-pointer">
<div class="w-12 h-12 flex items-center justify-center bg-primary/10 rounded-full mb-4">
<i class="ri-mental-health-line text-primary text-2xl"></i>
</div>
<h3 class="text-xl font-semibold text-gray-900 mb-2">Neurology</h3>
<p class="text-gray-600">98 Specialists Available</p>
</div>
<div id="neurologyModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
<div class="bg-white rounded-lg p-8 w-[1000px] max-h-[90vh] overflow-y-auto relative">
<button onclick="closeNeurologyModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<h2 class="text-3xl font-['Playfair_Display'] font-bold text-gray-900 mb-6">Neurology Department</h2>
<div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mb-8">
<div class="col-span-2">
<div class="bg-gray-50 p-6 rounded-lg mb-6">
<h3 class="text-xl font-semibold mb-4">Available Services</h3>
<div class="grid grid-cols-2 gap-4">
<div class="flex items-start space-x-3">
<i class="ri-brain-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Neurological Consultation</h4>
<p class="text-sm text-gray-600">Virtual consultation with neurologists</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-file-list-3-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">MRI/CT Review</h4>
<p class="text-sm text-gray-600">Expert analysis of brain scans</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-pulse-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">EEG Analysis</h4>
<p class="text-sm text-gray-600">Brain activity evaluation</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-medicine-bottle-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Treatment Planning</h4>
<p class="text-sm text-gray-600">Personalized care plans</p>
</div>
</div>
</div>
</div>
<div class="bg-white border rounded-lg p-6">
<h3 class="text-xl font-semibold mb-4">Available Time Slots</h3>
<div class="grid grid-cols-2 gap-4">
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectNeuroTimeSlot('2025-03-07 10:00', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 10:00 AM</p>
<p class="text-sm text-gray-600 relative">Dr. Rajesh Patel</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectNeuroTimeSlot('2025-03-07 13:30', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 01:30 PM</p>
<p class="text-sm text-gray-600 relative">Dr. Priya Sharma</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectNeuroTimeSlot('2025-03-07 15:00', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 03:00 PM</p>
<p class="text-sm text-gray-600 relative">Dr. Arun Kumar</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectNeuroTimeSlot('2025-03-07 17:30', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 05:30 PM</p>
<p class="text-sm text-gray-600 relative">Dr. Meera Reddy</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
</div>
</div>
</div>
<div class="bg-gray-50 p-6 rounded-lg">
<h3 class="text-xl font-semibold mb-4">Book Appointment</h3>
<form id="neurologyForm" class="space-y-4">
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Full Name</label>
<input type="text" id="neuroName" class="w-full px-3 py-2 border border-gray-300 rounded-md" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Age</label>
<input type="number" id="neuroAge" class="w-full px-3 py-2 border border-gray-300 rounded-md" required min="1" max="120">
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Selected Time Slot</label>
<input type="text" id="neuroTimeSlot" class="w-full px-3 py-2 border border-gray-300 rounded-md bg-gray-100" readonly>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Reason for Visit</label>
<textarea id="neuroReason" class="w-full px-3 py-2 border border-gray-300 rounded-md" rows="3" required></textarea>
</div>
<button type="submit" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:-translate-y-1 hover:shadow-lg active:translate-y-0 active:shadow-md">Book Appointment</button>
</form>
</div>
</div>
<div class="border-t mt-8 pt-8">
<h3 class="text-xl font-semibold mb-4">Our Neurologists</h3>
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/2ec030d735b81e25c67f708e4a21557d.jpg" alt="Dr. Rajesh Patel" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Rajesh Patel</h4>
<p class="text-sm text-center text-gray-600">Senior Neurologist</p>
<p class="text-xs text-center text-gray-500">MBBS, MD, DM (Neurology)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.9 (150+ reviews)</span>
</div>
</div>
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/c1645bc12b9897967f03023c2f08b8e2.jpg" alt="Dr. Priya Sharma" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Priya Sharma</h4>
<p class="text-sm text-center text-gray-600">Neuro-psychiatrist</p>
<p class="text-xs text-center text-gray-500">MBBS, MD (Psychiatry)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.8 (120+ reviews)</span>
</div>
</div>
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/de2e6a2e46c84d7c158e754a9feb05d6.jpg" alt="Dr. Arun Kumar" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Arun Kumar</h4>
<p class="text-sm text-center text-gray-600">Pediatric Neurologist</p>
<p class="text-xs text-center text-gray-500">MBBS, MD (Pediatrics), DM</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.9 (180+ reviews)</span>
</div>
</div>
</div>
</div>
</div>
</div>
<div onclick="openPsychiatryModal()" class="specialty-card bg-white p-6 rounded-lg shadow-sm cursor-pointer">
<div class="w-12 h-12 flex items-center justify-center bg-primary/10 rounded-full mb-4">
<i class="ri-psychotherapy-line text-primary text-2xl"></i>
</div>
<h3 class="text-xl font-semibold text-gray-900 mb-2">Psychiatry</h3>
<p class="text-gray-600">156 Specialists Available</p>
</div>
<div id="psychiatryModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
<div class="bg-white rounded-lg p-8 w-[1000px] max-h-[90vh] overflow-y-auto relative">
<button onclick="closePsychiatryModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<h2 class="text-3xl font-['Playfair_Display'] font-bold text-gray-900 mb-6">Psychiatry Department</h2>
<div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mb-8">
<div class="col-span-2">
<div class="bg-gray-50 p-6 rounded-lg mb-6">
<h3 class="text-xl font-semibold mb-4">Available Services</h3>
<div class="grid grid-cols-2 gap-4">
<div class="flex items-start space-x-3">
<i class="ri-mental-health-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Mental Health Consultation</h4>
<p class="text-sm text-gray-600">Virtual consultation with psychiatrists</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-psychotherapy-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Therapy Sessions</h4>
<p class="text-sm text-gray-600">Individual counseling</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-emotion-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Anxiety & Depression</h4>
<p class="text-sm text-gray-600">Specialized treatment</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-medicine-bottle-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Medication Management</h4>
<p class="text-sm text-gray-600">Prescription and monitoring</p>
</div>
</div>
</div>
</div>
<div class="bg-white border rounded-lg p-6">
<h3 class="text-xl font-semibold mb-4">Available Time Slots</h3>
<div class="grid grid-cols-2 gap-4">
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectPsychiatryTimeSlot('2025-03-07 10:30', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 10:30 AM</p>
<p class="text-sm text-gray-600 relative">Dr. Anjali Desai</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectPsychiatryTimeSlot('2025-03-07 13:00', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 01:00 PM</p>
<p class="text-sm text-gray-600 relative">Dr. Rahul Sharma</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectPsychiatryTimeSlot('2025-03-07 15:30', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 03:30 PM</p>
<p class="text-sm text-gray-600 relative">Dr. Priya Mehta</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectPsychiatryTimeSlot('2025-03-07 17:00', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 05:00 PM</p>
<p class="text-sm text-gray-600 relative">Dr. Sanjay Gupta</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
</div>
</div>
</div>
<div class="bg-gray-50 p-6 rounded-lg">
<h3 class="text-xl font-semibold mb-4">Book Appointment</h3>
<form id="psychiatryForm" class="space-y-4">
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Full Name</label>
<input type="text" id="psychiatryName" class="w-full px-3 py-2 border border-gray-300 rounded-md" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Age</label>
<input type="number" id="psychiatryAge" class="w-full px-3 py-2 border border-gray-300 rounded-md" required min="1" max="120">
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Selected Time Slot</label>
<input type="text" id="psychiatryTimeSlot" class="w-full px-3 py-2 border border-gray-300 rounded-md bg-gray-100" readonly>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Reason for Visit</label>
<textarea id="psychiatryReason" class="w-full px-3 py-2 border border-gray-300 rounded-md" rows="3" required></textarea>
</div>
<button type="submit" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:-translate-y-1 hover:shadow-lg active:translate-y-0 active:shadow-md">Book Appointment</button>
</form>
</div>
</div>
<div class="border-t mt-8 pt-8">
<h3 class="text-xl font-semibold mb-4">Our Psychiatrists</h3>
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/b83c909e47acbae197bb0aebf397cf67.jpg" alt="Dr. Anjali Desai" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Anjali Desai</h4>
<p class="text-sm text-center text-gray-600">Senior Psychiatrist</p>
<p class="text-xs text-center text-gray-500">MBBS, MD (Psychiatry)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.9 (180+ reviews)</span>
</div>
</div>
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/86b17169c0320083f91a36db6dcf2ea1.jpg" alt="Dr. Rahul Sharma" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Rahul Sharma</h4>
<p class="text-sm text-center text-gray-600">Child Psychiatrist</p>
<p class="text-xs text-center text-gray-500">MBBS, MD (Child Psychiatry)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.8 (150+ reviews)</span>
</div>
</div>
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/e394300ccd56c901e71e196e137c537c.jpg" alt="Dr. Priya Mehta" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Priya Mehta</h4>
<p class="text-sm text-center text-gray-600">Addiction Specialist</p>
<p class="text-xs text-center text-gray-500">MBBS, MD, DM (Addiction)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.9 (160+ reviews)</span>
</div>
</div>
</div>
</div>
</div>
</div>
<div onclick="openPulmonologyModal()" class="specialty-card bg-white p-6 rounded-lg shadow-sm cursor-pointer">
<div class="w-12 h-12 flex items-center justify-center bg-primary/10 rounded-full mb-4">
<i class="ri-lungs-line text-primary text-2xl"></i>
</div>
<h3 class="text-xl font-semibold text-gray-900 mb-2">Pulmonology</h3>
<p class="text-gray-600">87 Specialists Available</p>
</div>
<div id="pharmacyModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
<div class="bg-white rounded-lg p-8 w-[1000px] max-h-[90vh] overflow-y-auto relative">
<button onclick="closePharmacyModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<h2 class="text-3xl font-['Playfair_Display'] font-bold text-gray-900 mb-6">Online Pharmacy</h2>
<div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mb-8">
<div class="col-span-2">
<div class="bg-gray-50 p-6 rounded-lg mb-6">
<h3 class="text-xl font-semibold mb-4">Available Services</h3>
<div class="grid grid-cols-2 gap-4">
<div class="flex items-start space-x-3">
<i class="ri-medicine-bottle-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Prescription Medicines</h4>
<p class="text-sm text-gray-600">Upload prescription & get medicines delivered</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-truck-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Express Delivery</h4>
<p class="text-sm text-gray-600">Same day delivery available</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-24-hours-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">24/7 Service</h4>
<p class="text-sm text-gray-600">Order anytime</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-secure-payment-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Secure Payment</h4>
<p class="text-sm text-gray-600">Multiple payment options</p>
</div>
</div>
</div>
</div>
<div class="bg-white border rounded-lg p-6">
<h3 class="text-xl font-semibold mb-4">Popular Categories</h3>
<div class="grid grid-cols-2 gap-4">
<button onclick="showMedicineCategory('cardiac')" class="text-left p-4 border rounded-lg hover:bg-gray-50 flex items-center space-x-3">
<i class="ri-heart-pulse-line text-primary text-xl"></i>
<div>
<p class="font-medium">Cardiac Care</p>
<p class="text-sm text-gray-600">Heart & BP medicines</p>
</div>
</button>
<button onclick="showMedicineCategory('mental')" class="text-left p-4 border rounded-lg hover:bg-gray-50 flex items-center space-x-3">
<i class="ri-mental-health-line text-primary text-xl"></i>
<div>
<p class="font-medium">Mental Wellness</p>
<p class="text-sm text-gray-600">Stress & anxiety medicines</p>
</div>
</button>
<button onclick="showMedicineCategory('respiratory')" class="text-left p-4 border rounded-lg hover:bg-gray-50 flex items-center space-x-3">
<i class="ri-lungs-line text-primary text-xl"></i>
<div>
<p class="font-medium">Respiratory Care</p>
<p class="text-sm text-gray-600">Asthma & COPD medicines</p>
</div>
</button>
<button onclick="showMedicineCategory('diabetes')" class="text-left p-4 border rounded-lg hover:bg-gray-50 flex items-center space-x-3">
<i class="ri-capsule-line text-primary text-xl"></i>
<div>
<p class="font-medium">Diabetes Care</p>
<p class="text-sm text-gray-600">Diabetes medicines</p>
</div>
</button>
</div>
<div id="medicineList" class="mt-6 hidden">
<h4 class="text-lg font-semibold mb-4">Available Medicines</h4>
<div class="grid grid-cols-1 gap-4" id="medicineItems">
</div>
</div>
</div>
</div>
<div class="bg-gray-50 p-6 rounded-lg">
<h3 class="text-xl font-semibold mb-4">Order Medicines</h3>
<form id="pharmacyForm" class="space-y-4">
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Full Name</label>
<input type="text" id="pharmacyName" class="w-full px-3 py-2 border border-gray-300 rounded-md" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Delivery Address</label>
<textarea id="pharmacyAddress" class="w-full px-3 py-2 border border-gray-300 rounded-md" rows="2" required></textarea>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Phone Number</label>
<input type="tel" id="pharmacyPhone" class="w-full px-3 py-2 border border-gray-300 rounded-md" required pattern="[0-9]{10}">
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Upload Prescription</label>
<div class="mt-1 flex justify-center px-6 pt-5 pb-6 border-2 border-gray-300 border-dashed rounded-md">
<div class="space-y-1 text-center">
<i class="ri-upload-cloud-2-line text-gray-400 text-3xl"></i>
<div class="flex text-sm text-gray-600">
<label for="prescription-upload" class="relative cursor-pointer bg-white rounded-md font-medium text-primary hover:text-primary/90">
<span>Upload prescription</span>
<input id="prescription-upload" name="prescription-upload" type="file" class="sr-only" accept=".pdf,.jpg,.jpeg,.png">
</label>
</div>
<p class="text-xs text-gray-500">PDF, PNG, JPG up to 10MB</p>
</div>
</div>
</div>
<button type="submit" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">Place Order</button>
</form>
</div>
</div>
</div>
</div>
<div id="healthLeaveModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
<div class="bg-white rounded-lg p-8 w-[800px] max-h-[90vh] overflow-y-auto relative">
<button onclick="closeHealthLeaveModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<h2 class="text-3xl font-['Playfair_Display'] font-bold text-gray-900 mb-6">Generate Health Leave Certificate</h2>
<form id="healthLeaveForm" class="space-y-6">
<div class="grid grid-cols-2 gap-6">
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Full Name</label>
<input type="text" id="patientName" class="w-full px-3 py-2 border border-gray-300 rounded-md" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Age</label>
<input type="number" id="patientAge" class="w-full px-3 py-2 border border-gray-300 rounded-md" required min="1" max="120">
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Leave Start Date</label>
<input type="date" id="leaveStartDate" class="w-full px-3 py-2 border border-gray-300 rounded-md" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Number of Days</label>
<input type="number" id="leaveDays" class="w-full px-3 py-2 border border-gray-300 rounded-md" required min="1" max="30">
</div>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Medical Condition</label>
<select id="medicalCondition" class="w-full px-3 py-2 border border-gray-300 rounded-md" required>
<option value="">Select condition</option>
<option value="Fever">Fever</option>
<option value="Viral Infection">Viral Infection</option>
<option value="Food Poisoning">Food Poisoning</option>
<option value="Migraine">Migraine</option>
<option value="Acute Gastroenteritis">Acute Gastroenteritis</option>
<option value="Upper Respiratory Tract Infection">Upper Respiratory Tract Infection</option>
<option value="Lower Back Pain">Lower Back Pain</option>
<option value="Anxiety">Anxiety</option>
</select>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Symptoms Description</label>
<textarea id="symptoms" class="w-full px-3 py-2 border border-gray-300 rounded-md" rows="3" required></textarea>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Doctor's Remarks</label>
<textarea id="doctorRemarks" class="w-full px-3 py-2 border border-gray-300 rounded-md" rows="3" required></textarea>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Organization Details</label>
<input type="text" id="organization" class="w-full px-3 py-2 border border-gray-300 rounded-md" placeholder="Company/School Name" required>
</div>
<button type="submit" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">Generate Certificate</button>
</form>
</div>
</div>
<div id="pulmonologyModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
<div class="bg-white rounded-lg p-8 w-[1000px] max-h-[90vh] overflow-y-auto relative">
<button onclick="closePulmonologyModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<h2 class="text-3xl font-['Playfair_Display'] font-bold text-gray-900 mb-6">Pulmonology Department</h2>
<div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mb-8">
<div class="col-span-2">
<div class="bg-gray-50 p-6 rounded-lg mb-6">
<h3 class="text-xl font-semibold mb-4">Available Services</h3>
<div class="grid grid-cols-2 gap-4">
<div class="flex items-start space-x-3">
<i class="ri-lungs-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Respiratory Consultation</h4>
<p class="text-sm text-gray-600">Virtual consultation with pulmonologists</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-file-list-3-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Lung Function Tests</h4>
<p class="text-sm text-gray-600">Expert analysis of PFT reports</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-health-book-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Asthma Management</h4>
<p class="text-sm text-gray-600">Personalized treatment plans</p>
</div>
</div>
<div class="flex items-start space-x-3">
<i class="ri-medicine-bottle-line text-primary text-xl mt-1"></i>
<div>
<h4 class="font-medium">Sleep Studies</h4>
<p class="text-sm text-gray-600">Sleep apnea evaluation</p>
</div>
</div>
</div>
</div>
<div class="bg-white border rounded-lg p-6">
<h3 class="text-xl font-semibold mb-4">Available Time Slots</h3>
<div class="grid grid-cols-2 gap-4">
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectPulmonologyTimeSlot('2025-03-07 09:30', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 09:30 AM</p>
<p class="text-sm text-gray-600 relative">Dr. Amit Kumar</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectPulmonologyTimeSlot('2025-03-07 12:00', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 12:00 PM</p>
<p class="text-sm text-gray-600 relative">Dr. Neha Singh</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectPulmonologyTimeSlot('2025-03-07 14:30', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 02:30 PM</p>
<p class="text-sm text-gray-600 relative">Dr. Ravi Verma</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
<div class="text-center p-4 border rounded-lg cursor-pointer hover:bg-gray-50 relative group" onclick="selectPulmonologyTimeSlot('2025-03-07 16:00', this)">
<div class="absolute inset-0 bg-primary/10 opacity-0 group-hover:opacity-100 rounded-lg transition-opacity"></div>
<p class="font-medium relative">Today, 04:00 PM</p>
<p class="text-sm text-gray-600 relative">Dr. Priya Patel</p>
<div class="hidden absolute top-0 right-0 m-2 text-primary">
<i class="ri-check-line"></i>
</div>
</div>
</div>
</div>
</div>
<div class="bg-gray-50 p-6 rounded-lg">
<h3 class="text-xl font-semibold mb-4">Book Appointment</h3>
<form id="pulmonologyForm" class="space-y-4">
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Full Name</label>
<input type="text" id="pulmoName" class="w-full px-3 py-2 border border-gray-300 rounded-md" required>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Age</label>
<input type="number" id="pulmoAge" class="w-full px-3 py-2 border border-gray-300 rounded-md" required min="1" max="120">
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Selected Time Slot</label>
<input type="text" id="pulmoTimeSlot" class="w-full px-3 py-2 border border-gray-300 rounded-md bg-gray-100" readonly>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Reason for Visit</label>
<textarea id="pulmoReason" class="w-full px-3 py-2 border border-gray-300 rounded-md" rows="3" required></textarea>
</div>
<button type="submit" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:-translate-y-1 hover:shadow-lg active:translate-y-0 active:shadow-md">Book Appointment</button>
</form>
</div>
</div>
<div class="border-t mt-8 pt-8">
<h3 class="text-xl font-semibold mb-4">Our Pulmonologists</h3>
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/55676bf4dca0d0d9df6c5c83d2298ad4.jpg" alt="Dr. Amit Kumar" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Amit Kumar</h4>
<p class="text-sm text-center text-gray-600">Senior Pulmonologist</p>
<p class="text-xs text-center text-gray-500">MBBS, MD (Pulmonology)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.9 (140+ reviews)</span>
</div>
</div>
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/62bf74b7362dbdf736b8d64a18b8066b.jpg" alt="Dr. Neha Singh" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Neha Singh</h4>
<p class="text-sm text-center text-gray-600">Respiratory Specialist</p>
<p class="text-xs text-center text-gray-500">MBBS, DNB (Respiratory Medicine)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.8 (110+ reviews)</span>
</div>
</div>
<div class="bg-white p-4 rounded-lg border">
<img src="https://public.readdy.ai/ai/img_res/780b1290bf25cde8566c36985391f544.jpg" alt="Dr. Ravi Verma" class="w-24 h-24 rounded-full mx-auto mb-4 object-cover">
<h4 class="text-lg font-semibold text-center">Dr. Ravi Verma</h4>
<p class="text-sm text-center text-gray-600">Sleep Medicine Specialist</p>
<p class="text-xs text-center text-gray-500">MBBS, MD, DM (Pulmonology)</p>
<div class="flex justify-center items-center mt-2">
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-1 text-sm text-gray-600">4.9 (170+ reviews)</span>
</div>
</div>
</div>
</div>
</div>
</div>
</div>
</div>
</div>
</section>
<section id="featured-doctors" class="py-20 bg-gray-50">
<div class="glass-effect py-20">
<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
<div class="text-center mb-12">
<h2 class="text-4xl font-['Playfair_Display'] font-bold text-gray-900 mb-4">Featured Doctors</h2>
<p class="text-xl text-gray-600">Connect with top-rated healthcare professionals</p>
</div>
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
<div class="bg-white p-6 rounded-lg shadow-sm featured-doctor-card">
<img src="https://public.readdy.ai/ai/img_res/84c202b45553c1275f2634023fe21ab2.jpg" alt="Doctor" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
<h3 class="text-xl font-semibold text-gray-900 text-center mb-2">Dr. Priya Sharma</h3>
<p class="text-gray-600 text-center mb-4">Cardiologist</p>
<p class="text-sm text-gray-500 text-center mb-2">MBBS, MD (AIIMS Delhi)</p>
<div class="flex justify-center items-center space-x-1 mb-4">
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-2 text-gray-600">(128 reviews)</span>
</div>
<div class="text-center">
<button onclick="openConsultationModal(this)" data-doctor="Dr. Priya Sharma" data-specialty="Cardiologist" data-rating="4.9" data-reviews="128" class="px-6 py-2 text-sm font-medium text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:scale-105 hover:shadow-lg active:scale-100 active:shadow-md">Book Consultation</button>
</div>
</div>
<div class="bg-white p-6 rounded-lg shadow-sm featured-doctor-card">
<img src="https://public.readdy.ai/ai/img_res/2bb4e10621b1811dbb24deb3eb8bede4.jpg" alt="Doctor" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
<h3 class="text-xl font-semibold text-gray-900 text-center mb-2">Dr. Rajesh Patel</h3>
<p class="text-gray-600 text-center mb-4">Neurologist</p>
<p class="text-sm text-gray-500 text-center mb-2">MBBS, DM (NIMHANS Bangalore)</p>
<div class="flex justify-center items-center space-x-1 mb-4">
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-half-fill text-yellow-400"></i>
<span class="ml-2 text-gray-600">(96 reviews)</span>
</div>
<div class="text-center">
<button onclick="openConsultationModal(this)" data-doctor="Dr. Priya Sharma" data-specialty="Cardiologist" data-rating="4.9" data-reviews="128" class="px-6 py-2 text-sm font-medium text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:scale-105 hover:shadow-lg active:scale-100 active:shadow-md">Book Consultation</button>
</div>
</div>
<div class="bg-white p-6 rounded-lg shadow-sm featured-doctor-card">
<img src="https://public.readdy.ai/ai/img_res/3820a167347b46c277049385a064477c.jpg" alt="Doctor" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
<h3 class="text-xl font-semibold text-gray-900 text-center mb-2">Dr. Anjali Desai</h3>
<p class="text-gray-600 text-center mb-4">Psychiatrist</p>
<p class="text-sm text-gray-500 text-center mb-2">MBBS, MD (PGIMER Chandigarh)</p>
<div class="flex justify-center items-center space-x-1 mb-4">
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<i class="ri-star-fill text-yellow-400"></i>
<span class="ml-2 text-gray-600">(157 reviews)</span>
</div>
<div class="text-center">
<button onclick="openConsultationModal(this)" data-doctor="Dr. Priya Sharma" data-specialty="Cardiologist" data-rating="4.9" data-reviews="128" class="px-6 py-2 text-sm font-medium text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:scale-105 hover:shadow-lg active:scale-100 active:shadow-md">Book Consultation</button>
</div>
</div>
</div>
</div>
</div>
</section>
<section id="about" class="py-20 bg-white">
<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
<div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
<div>
<h2 class="text-4xl font-['Playfair_Display'] font-bold text-gray-900 mb-6">About DR.PERFECT</h2>
<p class="text-xl text-gray-600 mb-8">We're revolutionizing healthcare delivery through cutting-edge telemedicine technology, making quality healthcare accessible to everyone, everywhere.</p>
<div class="space-y-6 mb-8">
<p class="text-gray-600">Created by <span class="font-semibold">SANKET</span>, a first-year Biotechnology student at NIT Allahabad, DR.PERFECT aims to bridge the gap between patients and healthcare providers through virtual consultations.</p>
<p class="text-gray-600">Our mission is to provide rapid solutions for medical issues while offering doctors an opportunity to expand their practice into the virtual space.</p>
<div class="bg-white p-4 rounded-lg shadow-sm">
<h3 class="text-lg font-semibold text-gray-900 mb-2">Project Details</h3>
<ul class="space-y-2 text-gray-600">
<li><span class="font-medium">Development Time:</span> 2 Months and 12 Days</li>
<li><span class="font-medium">Developer:</span> Sanket</li>
<li><span class="font-medium">Status:</span> Frontend Model (Backend Under Construction)</li>
</ul>
</div>
</div>
<div class="grid grid-cols-2 gap-8 mb-8">
<div>
<div class="flex items-center mb-4">
<div class="w-12 h-12 flex items-center justify-center bg-primary/10 rounded-full stats-card">
<i class="ri-user-heart-line text-primary text-2xl"></i>
</div>
<h3 class="text-xl font-semibold text-gray-900 ml-4">10,000+</h3>
</div>
<p class="text-gray-600">Patients Served</p>
</div>
<div>
<div class="flex items-center mb-4">
<div class="w-12 h-12 flex items-center justify-center bg-primary/10 rounded-full stats-card">
<i class="ri-hospital-line text-primary text-2xl"></i>
</div>
<h3 class="text-xl font-semibold text-gray-900 ml-4">500+</h3>
</div>
<p class="text-gray-600">Certified Doctors</p>
</div>
<div>
<div class="flex items-center mb-4">
<div class="w-12 h-12 flex items-center justify-center bg-primary/10 rounded-full stats-card">
<i class="ri-global-line text-primary text-2xl"></i>
</div>
<h3 class="text-xl font-semibold text-gray-900 ml-4">50+</h3>
</div>
<p class="text-gray-600">Countries Covered</p>
</div>
<div>
<div class="flex items-center mb-4">
<div class="w-12 h-12 flex items-center justify-center bg-primary/10 rounded-full stats-card">
<i class="ri-service-line text-primary text-2xl"></i>
</div>
<h3 class="text-xl font-semibold text-gray-900 ml-4">20+</h3>
</div>
<p class="text-gray-600">Specialties</p>
</div>
</div>
<button onclick="openLearnMoreModal()" class="px-6 py-3 text-white bg-primary hover:bg-primary/90 !rounded-button">Learn More About Us</button>
<div id="learnMoreModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
<div class="bg-white rounded-lg p-8 w-[800px] max-h-[90vh] overflow-y-auto relative">
<button onclick="closeLearnMoreModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<h2 class="text-3xl font-['Playfair_Display'] font-bold text-gray-900 mb-6">About Our Medical Team</h2>
<div class="space-y-8">
<div class="border-b pb-6">
<h3 class="text-xl font-semibold mb-4">Our Medical Excellence</h3>
<p class="text-gray-600 mb-4">At DR.PERFECT, we take pride in our team of highly qualified medical professionals. Our doctors are selected through a rigorous verification process to ensure the highest standards of medical care.</p>
<div class="grid grid-cols-2 gap-4 text-sm">
<div class="bg-gray-50 p-4 rounded">
<p class="font-medium">Required Qualifications:</p>
<ul class="list-disc ml-4 mt-2 text-gray-600">
<li>Medical Degree from Accredited Institution</li>
<li>Valid Medical License</li>
<li>Board Certification in Specialty</li>
<li>Minimum 5 Years Clinical Experience</li>
</ul>
</div>
<div class="bg-gray-50 p-4 rounded">
<p class="font-medium">Additional Requirements:</p>
<ul class="list-disc ml-4 mt-2 text-gray-600">
<li>Telemedicine Certification</li>
<li>Regular CME Participation</li>
<li>Patient Satisfaction Rating > 4.5/5</li>
<li>Clear Communication Skills</li>
</ul>
</div>
</div>
</div>
<div class="border-b pb-6">
<h3 class="text-xl font-semibold mb-4">Featured Doctor Profiles</h3>
<div class="space-y-6">
<div class="flex gap-4 items-start">
<img src="https://public.readdy.ai/ai/img_res/fbe37017f440c4820f66096749e5b081.jpg" class="w-24 h-24 rounded-full object-cover">
<div>
<h4 class="font-semibold">Dr. Meera Reddy, MBBS, DM</h4>
<p class="text-primary">Cardiology</p>
<p class="text-sm text-gray-600 mt-2">
- AIIMS Delhi Gold Medalist<br>
- Senior Consultant at Apollo Hospitals<br>
- 15+ Years Clinical Experience<br>
- Published in Indian Heart Journal
</p>
</div>
</div>
<div class="flex gap-4 items-start">
<img src="https://public.readdy.ai/ai/img_res/49fc8eed88bf332bd74561d4525ec577.jpg" class="w-24 h-24 rounded-full object-cover">
<div>
<h4 class="font-semibold">Dr. Arun Kumar, MBBS, MD, DM</h4>
<p class="text-primary">Neurology</p>
<p class="text-sm text-gray-600 mt-2">
- NIMHANS Bangalore Alumni<br>
- Head of Neurology at Fortis Hospital<br>
- 12+ Years Clinical Experience<br>
- ICMR Research Fellowship
</p>
</div>
</div>
</div>
</div>
<div class="border-b pb-6">
<h3 class="text-xl font-semibold mb-4">Continuous Professional Development</h3>
<p class="text-gray-600 mb-4">Our doctors regularly participate in:</p>
<div class="grid grid-cols-2 gap-4">
<div class="bg-gray-50 p-4 rounded">
<i class="ri-award-line text-primary text-xl mb-2"></i>
<h5 class="font-medium mb-2">Medical Conferences</h5>
<p class="text-sm text-gray-600">Annual participation in international medical conferences and symposiums</p>
</div>
<div class="bg-gray-50 p-4 rounded">
<i class="ri-book-read-line text-primary text-xl mb-2"></i>
<h5 class="font-medium mb-2">Research Publications</h5>
<p class="text-sm text-gray-600">Regular contributions to peer-reviewed medical journals</p>
</div>
</div>
</div>
<div>
<h3 class="text-xl font-semibold mb-4">Quality Assurance</h3>
<div class="grid grid-cols-3 gap-4 text-center">
<div class="p-4">
<div class="text-3xl font-bold text-primary mb-2">98%</div>
<p class="text-sm text-gray-600">Patient Satisfaction Rate</p>
</div>
<div class="p-4">
<div class="text-3xl font-bold text-primary mb-2">24/7</div>
<p class="text-sm text-gray-600">Medical Support</p>
</div>
<div class="p-4">
<div class="text-3xl font-bold text-primary mb-2">100%</div>
<p class="text-sm text-gray-600">HIPAA Compliant</p>
</div>
</div>
</div>
</div>
</div>
</div>
</div>
<div>
<img src="https://public.readdy.ai/ai/img_res/f682ddd92419fb9eb42e79ef9691e3f7.jpg" alt="About Us" class="w-full h-full object-cover rounded-lg shadow-lg hero-image">
</div>
</div>
</div>
</div>
</section>
<section id="contact" class="py-20 bg-gray-50">
<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
<div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
<div>
<h2 class="text-4xl font-['Playfair_Display'] font-bold text-gray-900 mb-4">Contact Us</h2>
<p class="text-xl text-gray-600 mb-8">Have questions? We're here to help you get started with virtual consultations.</p>
<form class="space-y-6">
<div>
<label class="block text-sm font-medium text-gray-700 mb-2">Full Name</label>
<input type="text" class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" placeholder="Enter your full name">
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-2">Email</label>
<input type="email" class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" placeholder="Enter your email">
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-2">Specialty of Interest</label>
<select class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary">
<option value="">Select a specialty</option>
<option value="cardiology">Cardiology</option>
<option value="neurology">Neurology</option>
<option value="psychiatry">Psychiatry</option>
<option value="pulmonology">Pulmonology</option>
</select>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-2">Message</label>
<textarea class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary focus:border-primary" rows="4" placeholder="Your message"></textarea>
</div>
<button type="submit" class="w-full px-6 py-3 text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:-translate-y-1 hover:shadow-lg active:translate-y-0 active:shadow-md">Send Message</button>
</form>
</div>
<div class="lg:pl-12">
<img src="https://public.readdy.ai/ai/img_res/7e7562601ef3571161ce266701c8b35d.jpg" alt="Contact" class="w-full h-full object-cover rounded-lg">
</div>
</div>
</div>
</div>
</section>
<footer class="bg-gradient-to-r from-gray-900 via-gray-800 to-gray-900 text-white py-12">
<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
<div class="grid grid-cols-1 md:grid-cols-4 gap-8">
<div>
<h3 class="text-2xl font-['Playfair_Display'] font-bold mb-4">DR.PERFECT</h3>
<p class="text-gray-400">Connecting healthcare professionals with patients worldwide through secure virtual consultations.</p>
</div>
<div>
<h4 class="text-lg font-semibold mb-4">Quick Links</h4>
<ul class="space-y-2">
<li><a href="#" class="text-gray-400 hover:text-white">About Us</a></li>
<li><a href="#" class="text-gray-400 hover:text-white">How It Works</a></li>
<li><a href="#" class="text-gray-400 hover:text-white">For Doctors</a></li>
<li><a href="#" class="text-gray-400 hover:text-white">For Patients</a></li>
</ul>
</div>
<div>
<h4 class="text-lg font-semibold mb-4">Legal</h4>
<ul class="space-y-2">
<li><a href="#" class="text-gray-400 hover:text-white">Privacy Policy</a></li>
<li><a href="#" class="text-gray-400 hover:text-white">Terms of Service</a></li>
<li><a href="#" class="text-gray-400 hover:text-white">HIPAA Compliance</a></li>
</ul>
</div>
<div>
<h4 class="text-lg font-semibold mb-4">Connect</h4>
<div class="flex space-x-4">
<a href="#" class="text-gray-400 hover:text-white">
<i class="ri-facebook-fill text-2xl"></i>
</a>
<a href="#" class="text-gray-400 hover:text-white">
<i class="ri-twitter-fill text-2xl"></i>
</a>
<a href="https://www.linkedin.com/in/sanket-salunkhe-36a4b9329?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" target="_blank" class="text-gray-400 hover:text-white">
<i class="ri-linkedin-fill text-2xl"></i>
</a>
<a href="https://www.instagram.com/alt_sxnket_?igsh=MWlnNDFpOTg5c2psOA==" target="_blank" class="text-gray-400 hover:text-white">
<i class="ri-instagram-fill text-2xl"></i>
</a>
</div>
</div>
</div>
<div class="border-t border-gray-800 mt-12 pt-8 text-center">
<p class="text-gray-400">&copy; 2025 DR.PERFECT. All rights reserved. Created by Sanket, NIT Allahabad.</p>
</div>
</div>
</footer>
<div class="fixed bottom-4 right-4 chat-widget">
<button class="w-16 h-16 bg-primary rounded-full shadow-lg flex items-center justify-center cursor-pointer hover:bg-primary/90 transition-all duration-300 transform hover:scale-110 hover:rotate-12 active:scale-95 active:rotate-0">
<i class="ri-message-3-line text-white text-2xl"></i>
</button>
</div>
</main>
<script>
// Theme toggle functionality
const themeToggle = document.getElementById('themeToggle');
const html = document.documentElement;
// Check for saved theme preference, default to light
const savedTheme = localStorage.getItem('theme') || 'light';
html.classList.toggle('dark', savedTheme === 'dark');
// Handle theme toggle
themeToggle.addEventListener('click', () => {
const isDark = html.classList.toggle('dark');
localStorage.setItem('theme', isDark ? 'dark' : 'light');
// Optional: Animate the transition
document.body.style.transition = 'background-color 0.3s ease';
setTimeout(() => {
document.body.style.transition = '';
}, 300);
});
// Check system preference on load
if (savedTheme === 'system') {
const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
html.classList.toggle('dark', prefersDark);
}
// Listen for system theme changes
window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', (e) => {
if (localStorage.getItem('theme') === 'system') {
html.classList.toggle('dark', e.matches);
}
});
const bodyPartData = {
head: {
title: "Head & Brain",
description: "The head contains the brain, sensory organs, and is crucial for cognitive function.",
conditions: [
"Migraines",
"Concussion",
"Stroke",
"Brain Tumors"
],
specialists: [
"Neurologist",
"ENT Specialist",
"Ophthalmologist"
],
symptoms: [
"Headache",
"Dizziness",
"Vision Problems",
"Memory Issues"
]
},
chest: {
title: "Chest & Heart",
description: "The chest contains vital organs including the heart and lungs.",
conditions: [
"Coronary Artery Disease",
"Pneumonia",
"Asthma",
"Heart Arrhythmias"
],
specialists: [
"Cardiologist",
"Pulmonologist",
"Thoracic Surgeon"
],
symptoms: [
"Chest Pain",
"Shortness of Breath",
"Heart Palpitations",
"Persistent Cough"
]
},
abdomen: {
title: "Abdomen & Digestive System",
description: "The abdomen houses the digestive system and other vital organs.",
conditions: [
"Gastritis",
"Liver Disease",
"Kidney Stones",
"IBS"
],
specialists: [
"Gastroenterologist",
"Hepatologist",
"Nephrologist"
],
symptoms: [
"Abdominal Pain",
"Nausea",
"Bloating",
"Changes in Appetite"
]
},
arms: {
title: "Arms & Upper Limbs",
description: "The arms include bones, muscles, joints, and nerves essential for movement.",
conditions: [
"Carpal Tunnel Syndrome",
"Tennis Elbow",
"Arthritis",
"Rotator Cuff Injury"
],
specialists: [
"Orthopedist",
"Rheumatologist",
"Physical Therapist"
],
symptoms: [
"Joint Pain",
"Muscle Weakness",
"Numbness",
"Limited Range of Motion"
]
},
legs: {
title: "Legs & Lower Limbs",
description: "The legs support body weight and are crucial for mobility.",
conditions: [
"Deep Vein Thrombosis",
"Sciatica",
"Knee Osteoarthritis",
"Plantar Fasciitis"
],
specialists: [
"Orthopedist",
"Podiatrist",
"Vascular Surgeon"
],
symptoms: [
"Leg Pain",
"Swelling",
"Varicose Veins",
"Difficulty Walking"
]
}
};
let isNervousSystemView = false;
function showBodyPartInfo(part) {
const info = bodyPartData[part];
const infoDiv = document.getElementById('bodyPartInfo');
infoDiv.innerHTML = `
<h3 class="text-2xl font-semibold mb-4">${info.title}</h3>
<p class="text-gray-600 mb-4">${info.description}</p>
<div class="grid grid-cols-2 gap-4 mb-6">
<div>
<h4 class="font-semibold text-primary mb-2">Common Conditions</h4>
<ul class="list-disc list-inside text-gray-600">
${info.conditions.map(condition => `<li>${condition}</li>`).join('')}
</ul>
</div>
<div>
<h4 class="font-semibold text-primary mb-2">Key Symptoms</h4>
<ul class="list-disc list-inside text-gray-600">
${info.symptoms.map(symptom => `<li>${symptom}</li>`).join('')}
</ul>
</div>
</div>
<div>
<h4 class="font-semibold text-primary mb-2">Relevant Specialists</h4>
<div class="flex flex-wrap gap-2">
${info.specialists.map(specialist =>
`<span class="px-3 py-1 bg-primary/10 text-primary rounded-full text-sm">${specialist}</span>`
).join('')}
</div>
</div>
<button onclick="consultSpecialist('${part}')" class="mt-6 px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:scale-105 hover:shadow-lg active:scale-100 active:shadow-md">
Consult a Specialist
</button>
`;
}
function toggleNervousSystem() {
isNervousSystemView = !isNervousSystemView;
const bodyImage = document.getElementById('bodyImage');
const toggleButton = document.querySelector('[onclick="toggleNervousSystem()"]');
if (isNervousSystemView) {
bodyImage.src = "https://public.readdy.ai/ai/img_res/eb79a0eeb331357ccce1a19344da8c09.jpg";
toggleButton.innerHTML = 'Show Normal View';
toggleButton.classList.add('bg-gray-600');
toggleButton.classList.remove('bg-primary');
// Update clickable points for nervous system
const nervousSystemPoints = {
'brain': { top: '10%', left: '50%', title: 'Brain & Central Nervous System' },
'spine': { top: '40%', left: '50%', title: 'Spinal Cord' },
'peripheral': { top: '60%', left: '30%', title: 'Peripheral Nerves' },
'autonomic': { top: '70%', left: '50%', title: 'Autonomic Nervous System' }
};
const bodyPartContainer = document.querySelector('.body-part').parentElement;
bodyPartContainer.innerHTML = '';
Object.entries(nervousSystemPoints).forEach(([key, value]) => {
const point = document.createElement('div');
point.className = 'body-part';
point.style.cssText = `position: absolute; top: ${value.top}; left: ${value.left}; transform: translate(-50%, -50%);`;
point.innerHTML = `
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary group relative">
<div class="opacity-0 group-hover:opacity-100 absolute left-1/2 -translate-x-1/2 bottom-full mb-2 whitespace-nowrap bg-black text-white text-xs rounded px-2 py-1">
${value.title}
</div>
</div>`;
point.onclick = () => showNervousSystemInfo(key);
bodyPartContainer.appendChild(point);
});
} else {
bodyImage.src = "https://readdy.ai/api/search-image?query=anatomical illustration of human body with transparent layers showing muscles, bones and organs, medical textbook style, clean white background, professional medical illustration&width=600&height=800&seq=26&orientation=portrait";
toggleButton.innerHTML = 'Toggle Nervous System View';
toggleButton.classList.remove('bg-gray-600');
toggleButton.classList.add('bg-primary');
// Restore original body part points
const originalPoints = document.querySelector('.body-part').parentElement;
originalPoints.innerHTML = `
<div class="body-part" style="top: 10%; left: 50%; transform: translate(-50%, -50%);" onclick="showBodyPartInfo('head')">
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary"></div>
</div>
<div class="body-part" style="top: 25%; left: 50%; transform: translate(-50%, -50%);" onclick="showBodyPartInfo('chest')">
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary"></div>
</div>
<div class="body-part" style="top: 40%; left: 50%; transform: translate(-50%, -50%);" onclick="showBodyPartInfo('abdomen')">
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary"></div>
</div>
<div class="body-part" style="top: 60%; left: 30%; transform: translate(-50%, -50%);" onclick="showBodyPartInfo('arms')">
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary"></div>
</div>
<div class="body-part" style="top: 80%; left: 50%; transform: translate(-50%, -50%);" onclick="showBodyPartInfo('legs')">
<div class="w-4 h-4 bg-primary/50 rounded-full cursor-pointer hover:bg-primary"></div>
</div>`;
}
}
function showNervousSystemInfo(part) {
const nervousSystemData = {
brain: {
title: "Brain & Central Nervous System",
description: "The brain is the command center of the nervous system, controlling thoughts, memory, speech, movement and more.",
conditions: [
"Alzheimer's Disease",
"Brain Tumors",
"Epilepsy",
"Multiple Sclerosis"
],
symptoms: [
"Memory Loss",
"Seizures",
"Balance Problems",
"Speech Difficulties"
],
specialists: [
"Neurologist",
"Neurosurgeon",
"Neuropsychologist"
]
},
spine: {
title: "Spinal Cord",
description: "The spinal cord is the highway for communication between the brain and the rest of the body.",
conditions: [
"Spinal Cord Injury",
"Herniated Disc",
"Spinal Stenosis",
"Myelopathy"
],
symptoms: [
"Paralysis",
"Numbness",
"Weakness",
"Pain"
],
specialists: [
"Neurosurgeon",
"Orthopedic Surgeon",
"Pain Specialist"
]
},
peripheral: {
title: "Peripheral Nerves",
description: "Peripheral nerves connect the brain and spinal cord to the rest of the body.",
conditions: [
"Peripheral Neuropathy",
"Carpal Tunnel Syndrome",
"Guillain-Barré Syndrome",
"Diabetic Neuropathy"
],
symptoms: [
"Tingling",
"Burning Pain",
"Muscle Weakness",
"Loss of Sensation"
],
specialists: [
"Neurologist",
"Pain Management Specialist",
"Physical Therapist"
]
},
autonomic: {
title: "Autonomic Nervous System",
description: "Controls involuntary body functions like heart rate, digestion, and breathing.",
conditions: [
"Dysautonomia",
"Postural Orthostatic Tachycardia Syndrome",
"Autonomic Neuropathy",
"Raynaud's Disease"
],
symptoms: [
"Dizziness",
"Irregular Heartbeat",
"Digestive Problems",
"Temperature Regulation Issues"
],
specialists: [
"Neurologist",
"Cardiologist",
"Gastroenterologist"
]
}
};
const info = nervousSystemData[part];
const infoDiv = document.getElementById('bodyPartInfo');
infoDiv.innerHTML = `
<h3 class="text-2xl font-semibold mb-4">${info.title}</h3>
<p class="text-gray-600 mb-4">${info.description}</p>
<div class="grid grid-cols-2 gap-4 mb-6">
<div>
<h4 class="font-semibold text-primary mb-2">Common Conditions</h4>
<ul class="list-disc list-inside text-gray-600">
${info.conditions.map(condition => `<li>${condition}</li>`).join('')}
</ul>
</div>
<div>
<h4 class="font-semibold text-primary mb-2">Key Symptoms</h4>
<ul class="list-disc list-inside text-gray-600">
${info.symptoms.map(symptom => `<li>${symptom}</li>`).join('')}
</ul>
</div>
</div>
<div>
<h4 class="font-semibold text-primary mb-2">Relevant Specialists</h4>
<div class="flex flex-wrap gap-2">
${info.specialists.map(specialist =>
`<span class="px-3 py-1 bg-primary/10 text-primary rounded-full text-sm">${specialist}</span>`
).join('')}
</div>
</div>
<button onclick="consultSpecialist('${part}')" class="mt-6 px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button transition-all duration-300 transform hover:scale-105 hover:shadow-lg active:scale-100 active:shadow-md">
Consult a Specialist
</button>`;
}
function consultSpecialist(bodyPart) {
const specialists = bodyPartData[bodyPart].specialists;
const mainSpecialist = specialists[0];
// Open consultation modal with the main specialist
openConsultationModal({
getAttribute: (attr) => {
switch(attr) {
case 'data-doctor':
return `Dr. ${mainSpecialist.split(' ')[0]} Kumar`;
case 'data-specialty':
return mainSpecialist;
case 'data-rating':
return '4.9';
case 'data-reviews':
return '150+';
default:
return '';
}
}
});
}
function openSignInModal() {
document.getElementById('signInModal').classList.remove('hidden');
document.getElementById('registerModal')?.classList.add('hidden');
}
function closeSignInModal() {
document.getElementById('signInModal').classList.add('hidden');
}
function openRegisterModal() {
document.getElementById('registerModal').classList.remove('hidden');
document.getElementById('signInModal')?.classList.add('hidden');
}
function closeRegisterModal() {
document.getElementById('registerModal').classList.add('hidden');
}
function switchToSignIn() {
closeRegisterModal();
openSignInModal();
}
function openLearnMoreModal() {
document.getElementById('learnMoreModal').classList.remove('hidden');
}
function closeLearnMoreModal() {
document.getElementById('learnMoreModal').classList.add('hidden');
}
function openDoctorRegistration() {
openRegisterModal();
const userType = document.getElementById('userType');
userType.value = 'doctor';
const event = new Event('change');
userType.dispatchEvent(event);
document.getElementById('doctorFields').classList.remove('hidden');
document.getElementById('licenseNumber').required = true;
document.getElementById('specialty').required = true;
document.getElementById('registerName').focus();
}
function openCardiologyModal() {
document.getElementById('cardiologyModal').classList.remove('hidden');
}
function closeCardiologyModal() {
document.getElementById('cardiologyModal').classList.add('hidden');
}
function selectTimeSlot(time, element) {
document.getElementById('cardioTimeSlot').value = time;
// Remove selected state from all slots
const allSlots = document.querySelectorAll('.group');
allSlots.forEach(slot => {
slot.classList.remove('border-primary');
slot.querySelector('.ri-check-line').parentElement.classList.add('hidden');
});
// Add selected state to clicked slot
element.classList.add('border-primary');
element.querySelector('.ri-check-line').parentElement.classList.remove('hidden');
}
function selectNeuroTimeSlot(time, element) {
document.getElementById('neuroTimeSlot').value = time;
// Remove selected state from all slots
const allSlots = document.querySelectorAll('.group');
allSlots.forEach(slot => {
slot.classList.remove('border-primary');
slot.querySelector('.ri-check-line').parentElement.classList.add('hidden');
});
// Add selected state to clicked slot
element.classList.add('border-primary');
element.querySelector('.ri-check-line').parentElement.classList.remove('hidden');
}
function openNeurologyModal() {
document.getElementById('neurologyModal').classList.remove('hidden');
}
function closeNeurologyModal() {
document.getElementById('neurologyModal').classList.add('hidden');
}
function openPsychiatryModal() {
document.getElementById('psychiatryModal').classList.remove('hidden');
}
function closePsychiatryModal() {
document.getElementById('psychiatryModal').classList.add('hidden');
}
function openPulmonologyModal() {
document.getElementById('pulmonologyModal').classList.remove('hidden');
}
const medicineData = {
cardiac: [
{
name: "Amlodipine 5mg",
description: "Calcium channel blocker for blood pressure control",
price: "₹150",
prescription: true
},
{
name: "Metoprolol 25mg",
description: "Beta blocker for heart rate and blood pressure",
price: "₹200",
prescription: true
},
{
name: "Aspirin 75mg",
description: "Blood thinner for heart disease prevention",
price: "₹50",
prescription: false
}
],
mental: [
{
name: "Sertraline 50mg",
description: "SSRI antidepressant medication",
price: "₹300",
prescription: true
},
{
name: "Alprazolam 0.5mg",
description: "Anti-anxiety medication",
price: "₹250",
prescription: true
},
{
name: "Melatonin 3mg",
description: "Sleep aid supplement",
price: "₹180",
prescription: false
}
],
respiratory: [
{
name: "Salbutamol Inhaler",
description: "Bronchodilator for asthma relief",
price: "₹400",
prescription: true
},
{
name: "Montelukast 10mg",
description: "Anti-inflammatory for asthma control",
price: "₹350",
prescription: true
},
{
name: "Budesonide Nebulizer",
description: "Steroid for COPD treatment",
price: "₹600",
prescription: true
}
],
diabetes: [
{
name: "Metformin 500mg",
description: "Oral diabetes medication",
price: "₹120",
prescription: true
},
{
name: "Glimepiride 2mg",
description: "Sulfonylurea for blood sugar control",
price: "₹180",
prescription: true
},
{
name: "Blood Sugar Test Strips",
description: "For glucose monitoring",
price: "₹800",
prescription: false
}
]
};
function showMedicineCategory(category) {
const medicineList = document.getElementById('medicineList');
const medicineItems = document.getElementById('medicineItems');
medicineItems.innerHTML = '';
medicineData[category].forEach(medicine => {
const medicineCard = document.createElement('div');
medicineCard.className = 'border rounded-lg p-4 flex justify-between items-center';
medicineCard.innerHTML = `
<div>
<h5 class="font-medium">${medicine.name}</h5>
<p class="text-sm text-gray-600">${medicine.description}</p>
<p class="text-primary font-medium mt-1">${medicine.price}</p>
</div>
<div class="flex items-center gap-2">
${medicine.prescription ?
'<span class="text-xs bg-red-100 text-red-600 px-2 py-1 rounded">Prescription Required</span>' :
'<span class="text-xs bg-green-100 text-green-600 px-2 py-1 rounded">OTC</span>'
}
<button onclick="addToCart('${medicine.name}', '${medicine.price}')" class="px-3 py-1 text-sm text-white bg-primary hover:bg-primary/90 rounded-md">
Add to Cart
</button>
</div>
`;
medicineItems.appendChild(medicineCard);
});
medicineList.classList.remove('hidden');
}
function addToCart(medicineName, price) {
const successToast = document.createElement('div');
successToast.className = 'fixed bottom-4 left-1/2 transform -translate-x-1/2 bg-green-500 text-white px-6 py-3 rounded-lg shadow-lg z-50';
successToast.innerHTML = `
<div class="flex items-center gap-2">
<i class="ri-check-line"></i>
<span>${medicineName} added to cart - ${price}</span>
</div>
`;
document.body.appendChild(successToast);
setTimeout(() => {
successToast.remove();
}, 3000);
}
function closePharmacyModal() {
document.getElementById('pharmacyModal').classList.add('hidden');
const medicineList = document.getElementById('medicineList');
medicineList.classList.add('hidden');
}
function openPharmacyModal() {
document.getElementById('pharmacyModal').classList.remove('hidden');
}
document.addEventListener('DOMContentLoaded', function() {
const pharmacyForm = document.getElementById('pharmacyForm');
if(pharmacyForm) {
pharmacyForm.addEventListener('submit', function(e) {
e.preventDefault();
const name = document.getElementById('pharmacyName').value;
const address = document.getElementById('pharmacyAddress').value;
const phone = document.getElementById('pharmacyPhone').value;
const successModal = document.createElement('div');
successModal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-[60]';
successModal.innerHTML = `
<div class="bg-white rounded-lg p-6 w-96">
<h3 class="text-xl font-semibold mb-4">Order Placed Successfully!</h3>
<p class="text-gray-600 mb-2">Dear ${name},</p>
<p class="text-gray-600 mb-4">Your medicine order has been received and will be delivered to:</p>
<p class="text-gray-600 mb-4">${address}</p>
<p class="text-gray-600 mb-4">Our pharmacist will review your prescription and contact you at ${phone} if needed.</p>
<p class="text-gray-600 mb-4">Expected delivery: Within 24 hours</p>
<button onclick="this.parentElement.parentElement.remove(); closePharmacyModal();" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">OK</button>
</div>
`;
document.body.appendChild(successModal);
pharmacyForm.reset();
});
}
document.getElementById('prescription-upload')?.addEventListener('change', function(e) {
const file = e.target.files[0];
if (file) {
const fileName = file.name;
const fileSize = (file.size / 1024 / 1024).toFixed(2);
const preview = document.createElement('div');
preview.className = 'mt-2 text-sm text-gray-500';
preview.innerHTML = `Selected file: ${fileName} (${fileSize} MB)`;
const container = e.target.closest('div');
const existingPreview = container.querySelector('.mt-2');
if (existingPreview) {
existingPreview.remove();
}
container.appendChild(preview);
}
});
});
function closeHealthLeaveModal() {
document.getElementById('healthLeaveModal').classList.add('hidden');
}
function openHealthLeaveModal() {
document.getElementById('healthLeaveModal').classList.remove('hidden');
const today = new Date().toISOString().split('T')[0];
document.getElementById('leaveStartDate').min = today;
// Add event listeners for form fields
document.getElementById('medicalCondition').addEventListener('change', function(e) {
const condition = e.target.value;
const symptomsField = document.getElementById('symptoms');
const remarksField = document.getElementById('doctorRemarks');
// Pre-fill symptoms and remarks based on condition
const conditionData = {
'Fever': {
symptoms: 'High temperature (38.5°C), body aches, fatigue, and mild dehydration.',
remarks: 'Patient requires bed rest and adequate hydration. Prescribed antipyretics and rest for recovery.'
},
'Viral Infection': {
symptoms: 'Fever, sore throat, runny nose, body aches, and general weakness.',
remarks: 'Symptomatic treatment advised. Patient should avoid contact with others to prevent spread.'
},
'Food Poisoning': {
symptoms: 'Severe stomach cramps, vomiting, diarrhea, and mild dehydration.',
remarks: 'Oral rehydration and rest recommended. Prescribed anti-emetics and probiotics.'
},
'Migraine': {
symptoms: 'Severe headache, sensitivity to light and sound, nausea.',
remarks: 'Patient needs rest in a quiet, dark environment. Prescribed appropriate medication.'
},
'Acute Gastroenteritis': {
symptoms: 'Abdominal pain, frequent loose stools, vomiting, and dehydration.',
remarks: 'Requires rest and fluid replacement. Prescribed anti-diarrheal medication and electrolytes.'
},
'Upper Respiratory Tract Infection': {
symptoms: 'Nasal congestion, cough, sore throat, and mild fever.',
remarks: 'Symptomatic treatment with rest advised. Prescribed decongestants and cough suppressants.'
},
'Lower Back Pain': {
symptoms: 'Acute lower back pain, difficulty in movement, muscle spasm.',
remarks: 'Physical rest needed. Prescribed pain relievers and muscle relaxants.'
},
'Anxiety': {
symptoms: 'Acute anxiety symptoms, difficulty concentrating, physical manifestations of stress.',
remarks: 'Short period of rest recommended for recovery. Supportive care and stress management advised.'
}
};
if (conditionData[condition]) {
symptomsField.value = conditionData[condition].symptoms;
remarksField.value = conditionData[condition].remarks;
}
});
// Handle form submission
document.getElementById('healthLeaveForm').addEventListener('submit', function(e) {
e.preventDefault();
const formData = {
name: document.getElementById('patientName').value,
age: document.getElementById('patientAge').value,
startDate: document.getElementById('leaveStartDate').value,
days: document.getElementById('leaveDays').value,
condition: document.getElementById('medicalCondition').value,
symptoms: document.getElementById('symptoms').value,
remarks: document.getElementById('doctorRemarks').value,
organization: document.getElementById('organization').value
};
// Create certificate preview modal
const certificateModal = document.createElement('div');
certificateModal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-[60]';
const currentDate = new Date().toLocaleDateString('en-US', { year: 'numeric', month: 'long', day: 'numeric' });
certificateModal.innerHTML = `
<div class="bg-white rounded-lg p-8 w-[800px] max-h-[90vh] overflow-y-auto relative">
<button onclick="this.parentElement.parentElement.remove()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<div class="border-4 border-primary/20 p-8 rounded-lg">
<div class="text-center mb-8">
<h2 class="text-3xl font-['Playfair_Display'] font-bold text-primary mb-2">Medical Certificate</h2>
<p class="text-gray-600">DR.PERFECT Virtual Medical Consultations</p>
<p class="text-gray-600">Reg. No: DRP-${Math.random().toString(36).substr(2, 8).toUpperCase()}</p>
</div>
<div class="space-y-4">
<p class="text-gray-800">This is to certify that Mr./Ms. <span class="font-semibold">${formData.name}</span>, aged ${formData.age} years, is suffering from <span class="font-semibold">${formData.condition}</span>.</p>
<p class="text-gray-800">Clinical Findings:</p>
<p class="text-gray-600 pl-4">${formData.symptoms}</p>
<p class="text-gray-800">Doctor's Remarks:</p>
<p class="text-gray-600 pl-4">${formData.remarks}</p>
<p class="text-gray-800 mt-6">In view of the above, ${formData.days} day(s) of medical leave is recommended from ${new Date(formData.startDate).toLocaleDateString('en-US', { year: 'numeric', month: 'long', day: 'numeric' })}.</p>
<div class="mt-8 pt-8 border-t">
<div class="flex justify-between items-end">
<div>
<p class="text-gray-600">Date: ${currentDate}</p>
<p class="text-gray-600">Valid for: ${formData.organization}</p>
</div>
<div class="text-right">
<img src="https://public.readdy.ai/ai/img_res/65447c4c0c979e5c02bb935ede29a9df.jpg" alt="Doctor's Signature" class="w-40 h-20 object-contain mb-2">
<p class="font-semibold">Dr. Rajesh Kumar</p>
<p class="text-gray-600">MD, General Medicine</p>
<p class="text-gray-600">Reg. No: IMC-${Math.random().toString(36).substr(2, 8).toUpperCase()}</p>
</div>
</div>
</div>
</div>
</div>
<div class="mt-6 flex justify-center">
<button onclick="window.print()" class="px-6 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">
<i class="ri-printer-line mr-2"></i>Print Certificate
</button>
</div>
</div>
`;
document.body.appendChild(certificateModal);
closeHealthLeaveModal();
});
}
function closePulmonologyModal() {
document.getElementById('pulmonologyModal').classList.add('hidden');
}
function selectPulmonologyTimeSlot(time, element) {
document.getElementById('pulmoTimeSlot').value = time;
// Remove selected state from all slots
const allSlots = document.querySelectorAll('.group');
allSlots.forEach(slot => {
slot.classList.remove('border-primary');
slot.querySelector('.ri-check-line').parentElement.classList.add('hidden');
});
// Add selected state to clicked slot
element.classList.add('border-primary');
element.querySelector('.ri-check-line').parentElement.classList.remove('hidden');
}
function selectPsychiatryTimeSlot(time, element) {
document.getElementById('psychiatryTimeSlot').value = time;
// Remove selected state from all slots
const allSlots = document.querySelectorAll('.group');
allSlots.forEach(slot => {
slot.classList.remove('border-primary');
slot.querySelector('.ri-check-line').parentElement.classList.add('hidden');
});
// Add selected state to clicked slot
element.classList.add('border-primary');
element.querySelector('.ri-check-line').parentElement.classList.remove('hidden');
}
document.addEventListener('DOMContentLoaded', function() {
const cardiologyForm = document.getElementById('cardiologyForm');
const neurologyForm = document.getElementById('neurologyForm');
const pulmonologyForm = document.getElementById('pulmonologyForm');
if(pulmonologyForm) {
pulmonologyForm.addEventListener('submit', function(e) {
e.preventDefault();
const name = document.getElementById('pulmoName').value;
const age = document.getElementById('pulmoAge').value;
const timeSlot = document.getElementById('pulmoTimeSlot').value;
const reason = document.getElementById('pulmoReason').value;
if(!timeSlot) {
const errorDiv = document.createElement('div');
errorDiv.className = 'text-red-500 text-sm mt-2';
errorDiv.textContent = 'Please select a time slot';
pulmonologyForm.appendChild(errorDiv);
setTimeout(() => errorDiv.remove(), 3000);
return;
}
const successModal = document.createElement('div');
successModal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-[60]';
successModal.innerHTML = `
<div class="bg-white rounded-lg p-6 w-96">
<h3 class="text-xl font-semibold mb-4">Pulmonology Appointment Confirmed!</h3>
<p class="text-gray-600 mb-2">Dear ${name},</p>
<p class="text-gray-600 mb-4">Your pulmonology appointment has been scheduled for ${timeSlot}.</p>
<p class="text-gray-600 mb-4">Please arrive 15 minutes before your scheduled time. Don't forget to bring any relevant medical records, chest X-rays, or test results.</p>
<button onclick="this.parentElement.parentElement.remove(); closePulmonologyModal();" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">OK</button>
</div>
`;
document.body.appendChild(successModal);
pulmonologyForm.reset();
});
}
if(neurologyForm) {
neurologyForm.addEventListener('submit', function(e) {
const psychiatryForm = document.getElementById('psychiatryForm');
if(psychiatryForm) {
psychiatryForm.addEventListener('submit', function(e) {
e.preventDefault();
const name = document.getElementById('psychiatryName').value;
const age = document.getElementById('psychiatryAge').value;
const timeSlot = document.getElementById('psychiatryTimeSlot').value;
const reason = document.getElementById('psychiatryReason').value;
if(!timeSlot) {
const errorDiv = document.createElement('div');
errorDiv.className = 'text-red-500 text-sm mt-2';
errorDiv.textContent = 'Please select a time slot';
psychiatryForm.appendChild(errorDiv);
setTimeout(() => errorDiv.remove(), 3000);
return;
}
const successModal = document.createElement('div');
successModal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-[60]';
successModal.innerHTML = `
<div class="bg-white rounded-lg p-6 w-96">
<h3 class="text-xl font-semibold mb-4">Psychiatry Appointment Confirmed!</h3>
<p class="text-gray-600 mb-2">Dear ${name},</p>
<p class="text-gray-600 mb-4">Your psychiatry appointment has been scheduled for ${timeSlot}.</p>
<p class="text-gray-600 mb-4">Please arrive 15 minutes before your scheduled time. Your privacy and confidentiality are our top priorities.</p>
<button onclick="this.parentElement.parentElement.remove(); closePsychiatryModal();" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">OK</button>
</div>
`;
document.body.appendChild(successModal);
psychiatryForm.reset();
});
}
e.preventDefault();
const name = document.getElementById('neuroName').value;
const age = document.getElementById('neuroAge').value;
const timeSlot = document.getElementById('neuroTimeSlot').value;
const reason = document.getElementById('neuroReason').value;
if(!timeSlot) {
const errorDiv = document.createElement('div');
errorDiv.className = 'text-red-500 text-sm mt-2';
errorDiv.textContent = 'Please select a time slot';
neurologyForm.appendChild(errorDiv);
setTimeout(() => errorDiv.remove(), 3000);
return;
}
const successModal = document.createElement('div');
successModal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-[60]';
successModal.innerHTML = `
<div class="bg-white rounded-lg p-6 w-96">
<h3 class="text-xl font-semibold mb-4">Neurology Appointment Confirmed!</h3>
<p class="text-gray-600 mb-2">Dear ${name},</p>
<p class="text-gray-600 mb-4">Your neurology appointment has been scheduled for ${timeSlot}.</p>
<p class="text-gray-600 mb-4">Please arrive 15 minutes before your scheduled time. Don't forget to bring any relevant medical records, brain scans, or test results.</p>
<button onclick="this.parentElement.parentElement.remove(); closeNeurologyModal();" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">OK</button>
</div>
`;
document.body.appendChild(successModal);
neurologyForm.reset();
});
}
if(cardiologyForm) {
cardiologyForm.addEventListener('submit', function(e) {
e.preventDefault();
const name = document.getElementById('cardioName').value;
const age = document.getElementById('cardioAge').value;
const timeSlot = document.getElementById('cardioTimeSlot').value;
const reason = document.getElementById('cardioReason').value;
if(!timeSlot) {
const errorDiv = document.createElement('div');
errorDiv.className = 'text-red-500 text-sm mt-2';
errorDiv.textContent = 'Please select a time slot';
cardiologyForm.appendChild(errorDiv);
setTimeout(() => errorDiv.remove(), 3000);
return;
}
const successModal = document.createElement('div');
successModal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-[60]';
successModal.innerHTML = `
<div class="bg-white rounded-lg p-6 w-96">
<h3 class="text-xl font-semibold mb-4">Appointment Confirmed!</h3>
<p class="text-gray-600 mb-2">Dear ${name},</p>
<p class="text-gray-600 mb-4">Your cardiology appointment has been scheduled for ${timeSlot}.</p>
<p class="text-gray-600 mb-4">Please arrive 15 minutes before your scheduled time. Don't forget to bring any relevant medical records or test results.</p>
<button onclick="this.parentElement.parentElement.remove(); closeCardiologyModal();" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">OK</button>
</div>
`;
document.body.appendChild(successModal);
cardiologyForm.reset();
});
}
});
document.addEventListener('DOMContentLoaded', function() {
const signInForm = document.getElementById('signInForm');
const registerForm = document.getElementById('registerForm');
const userType = document.getElementById('userType');
const doctorFields = document.getElementById('doctorFields');
userType.addEventListener('change', function() {
if(this.value === 'doctor') {
doctorFields.classList.remove('hidden');
document.getElementById('licenseNumber').required = true;
document.getElementById('specialty').required = true;
} else {
doctorFields.classList.add('hidden');
document.getElementById('licenseNumber').required = false;
document.getElementById('specialty').required = false;
}
});
registerForm.addEventListener('submit', function(e) {
e.preventDefault();
const name = document.getElementById('registerName').value;
const email = document.getElementById('registerEmail').value;
const password = document.getElementById('registerPassword').value;
const confirmPassword = document.getElementById('confirmPassword').value;
const type = document.getElementById('userType').value;
const terms = document.getElementById('terms').checked;
if(password !== confirmPassword) {
const errorDiv = document.createElement('div');
errorDiv.className = 'text-red-500 text-sm mt-2';
errorDiv.textContent = 'Passwords do not match';
registerForm.appendChild(errorDiv);
setTimeout(() => errorDiv.remove(), 3000);
return;
}
if(!terms) {
const errorDiv = document.createElement('div');
errorDiv.className = 'text-red-500 text-sm mt-2';
errorDiv.textContent = 'Please accept the terms and conditions';
registerForm.appendChild(errorDiv);
setTimeout(() => errorDiv.remove(), 3000);
return;
}
const successModal = document.createElement('div');
successModal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50';
successModal.innerHTML = `
<div class="bg-white rounded-lg p-6 w-96">
<h3 class="text-xl font-semibold mb-4">Registration Successful!</h3>
<p class="text-gray-600 mb-2">Welcome, ${name}!</p>
<p class="text-gray-600 mb-4">You have successfully registered as a ${type}.</p>
<button onclick="this.parentElement.parentElement.remove()" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">Continue</button>
</div>
`;
document.body.appendChild(successModal);
closeRegisterModal();
registerForm.reset();
});
signInForm.addEventListener('submit', function(e) {
e.preventDefault();
const email = document.getElementById('signInEmail').value;
const password = document.getElementById('signInPassword').value;
const remember = document.getElementById('remember').checked;
const mockUserData = {
email: "doctor@example.com",
password: "password123",
name: "Dr. John Smith",
specialty: "Cardiology",
lastLogin: "2025-03-07 09:30:00"
};
if(email === mockUserData.email && password === mockUserData.password) {
const successModal = document.createElement('div');
successModal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50';
successModal.innerHTML = `
<div class="bg-white rounded-lg p-6 w-96">
<h3 class="text-xl font-semibold mb-4">Welcome back, ${mockUserData.name}!</h3>
<p class="text-gray-600 mb-2">Specialty: ${mockUserData.specialty}</p>
<p class="text-gray-600 mb-4">Last login: ${mockUserData.lastLogin}</p>
<button onclick="this.parentElement.parentElement.remove()" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">Continue</button>
</div>
`;
document.body.appendChild(successModal);
closeSignInModal();
signInForm.reset();
} else {
const errorDiv = document.createElement('div');
errorDiv.className = 'text-red-500 text-sm mt-2';
errorDiv.textContent = 'Invalid email or password';
signInForm.appendChild(errorDiv);
setTimeout(() => errorDiv.remove(), 3000);
}
});
// Navigation handling
const navLinks = document.querySelectorAll('nav a');
navLinks.forEach(link => {
link.addEventListener('click', function(e) {
e.preventDefault();
const targetId = this.getAttribute('href').substring(1);
if(targetId) {
const targetSection = document.getElementById(targetId);
if(targetSection) {
window.scrollTo({
top: targetSection.offsetTop - 64,
behavior: 'smooth'
});
}
} else {
window.scrollTo({
top: 0,
behavior: 'smooth'
});
}
});
});
const chatWidget = document.querySelector('.chat-widget');
let chatWindow = null;
function getAIResponse(message) {
const medicalKnowledge = {
"headache": "Based on my medical knowledge, headaches can be caused by various factors including stress, dehydration, lack of sleep, or underlying medical conditions. Common types include tension headaches, migraines, and cluster headaches. I recommend consulting our neurologists for persistent headaches. Would you like me to help you schedule an appointment?",
"fever": "As a medical AI, I can tell you that fever is usually a sign that your body is fighting an infection. Normal body temperature is around 98.6°F (37°C). If your temperature exceeds 103°F (39.4°C) or persists for more than 3 days, I strongly recommend seeking medical attention. Would you like to discuss your symptoms in more detail?",
"diabetes": "Let me explain diabetes in detail. It's a chronic condition affecting how your body processes glucose. There are two main types: Type 1 (body doesn't produce insulin) and Type 2 (body doesn't use insulin effectively). I recommend a comprehensive management approach including diet, exercise, and medication. Would you like to learn more about any specific aspect?",
"blood pressure": "From my medical database, normal blood pressure is typically around 120/80 mmHg. Hypertension (high blood pressure) is generally considered 130/80 mmHg or higher. I can help you understand lifestyle changes and medications that can help manage blood pressure. Would you like to schedule a consultation with our specialists?",
"covid": "Based on current medical guidelines, COVID-19 symptoms include fever, cough, fatigue, and loss of taste/smell. If you're experiencing these symptoms, I strongly recommend getting tested and isolating. Our pulmonologists can provide virtual consultations. Shall I help you book an appointment?",
"heart": "Heart health is a crucial aspect I frequently discuss with patients. Common conditions include coronary artery disease, arrhythmias, and heart failure. Risk factors include high blood pressure, high cholesterol, smoking, and obesity. I recommend regular check-ups with our cardiologists. Would you like to know more about any specific heart condition?",
"cancer": "As an AI medical assistant, I understand that cancer is a serious concern. It's characterized by abnormal cell growth, and early detection is key for successful treatment. I strongly recommend regular screenings. Let me connect you with appropriate specialists based on specific cancer types. Would you like to discuss this further?",
"pregnancy": "Congratulations if you're expecting! Pregnancy typically lasts 40 weeks, divided into three trimesters. As your virtual medical assistant, I emphasize that regular prenatal care is essential. Our specialists can provide detailed guidance on nutrition, exercise, and managing pregnancy-related conditions. Would you like to schedule a consultation?",
"vaccination": "Based on current medical protocols, vaccinations are crucial for disease prevention. I can help you understand the standard immunization schedule and provide personalized vaccination advice based on your age and health conditions. Would you like to review your vaccination status?",
"mental health": "I want you to know that mental health is as important as physical health. Common conditions I often discuss include anxiety, depression, and stress-related disorders. Our psychiatrists provide confidential consultations and personalized treatment plans. Would you like to talk about any specific concerns?",
"nutrition": "Let me share some important nutrition principles. A balanced diet should include proteins, carbohydrates, healthy fats, vitamins, and minerals. I can help you develop a personalized nutrition plan. Would you like specific dietary recommendations?",
"exercise": "As your health assistant, I recommend 150 minutes of moderate aerobic activity or 75 minutes of vigorous activity per week. I can help you develop an exercise plan that suits your lifestyle and health goals. Would you like to discuss this further?",
"sleep": "Sleep is crucial for your health. Adults typically need 7-9 hours per night. I can provide detailed sleep hygiene advice and connect you with our specialists if you're experiencing sleep disorders. Would you like some specific sleep improvement tips?",
"allergies": "I understand dealing with allergies can be challenging. They occur when your immune system reacts to normally harmless substances. Common allergens include pollen, dust, food, and medications. I can help identify triggers and develop treatment plans. Would you like to discuss your specific allergy symptoms?",
"default": "I'm Dr. AI, your virtual medical assistant. While I can provide general medical information and guidance, for specific medical advice, I recommend consulting with our specialists. I'm here to help you understand your health concerns and connect you with the right healthcare professionals. What would you like to know more about?"
};
const lowercaseMsg = message.toLowerCase();
// Check for basic greetings first
if (lowercaseMsg.includes("hello") || lowercaseMsg.includes("hi")) {
return "Hello! I'm Dr. AI, your personal virtual medical assistant from DR.PERFECT. I have extensive knowledge in various medical fields and can help you understand health conditions, symptoms, and treatments. I can also connect you with our specialists for professional medical care. How may I assist you today?";
}
// Check for appointment-related queries
if (lowercaseMsg.includes("appointment")) {
return "As your virtual medical assistant, I'd be happy to help you schedule an appointment. We have highly qualified specialists in Cardiology, Neurology, Psychiatry, and Pulmonology. To ensure you get the most appropriate care, could you tell me more about your symptoms or health concerns? This will help me recommend the right specialist for you.";
}
// Check for doctor-related queries
if (lowercaseMsg.includes("doctor")) {
return "Let me tell you about our exceptional medical team. We have highly qualified specialists across various fields, each with extensive experience and expertise in their respective areas. Our doctors are carefully selected and maintain the highest standards of medical care. Would you like to learn more about a specific specialty, or shall I help you schedule a consultation with one of our experts?";
}
// Check for medical knowledge
for (const [keyword, info] of Object.entries(medicalKnowledge)) {
if (lowercaseMsg.includes(keyword)) {
return info;
}
}
// Check for symptoms
if (lowercaseMsg.includes("symptom") || lowercaseMsg.includes("pain") || lowercaseMsg.includes("feel")) {
return "I understand you're experiencing some health concerns. As a medical AI, I can help analyze your symptoms and provide general guidance. However, for your safety and to ensure accurate diagnosis, I strongly recommend consulting with our medical professionals. Could you describe your symptoms in more detail? This will help me better understand your situation and recommend the most appropriate specialist for your needs. Would you like to schedule an appointment with one of our experts?";
}
// Emergency situations
if (lowercaseMsg.includes("emergency") || lowercaseMsg.includes("urgent")) {
return "I need to emphasize this important point: If you're experiencing a medical emergency such as severe chest pain, difficulty breathing, severe bleeding, or other life-threatening symptoms, please call emergency services immediately (911) or visit the nearest emergency room. Your safety is our top priority. For non-emergency but urgent situations, I can help you schedule a priority consultation with our specialists. Could you briefly describe what you're experiencing so I can better assist you?";
}
return medicalKnowledge.default;
}
function getResponse(message) {
return getAIResponse(message);
}
function createChatMessage(message, isUser = false) {
const messageDiv = document.createElement('div');
messageDiv.className = `flex ${isUser ? 'justify-end' : 'justify-start'} mb-3`;
messageDiv.innerHTML = `
<div class="${isUser ? 'bg-primary text-white' : 'bg-white border'} rounded-lg px-4 py-2 max-w-[80%] shadow-sm">
<p class="text-sm">${message.split('\n').join('<br>')}</p>
</div>
`;
return messageDiv;
}
function getResponse(message) {
return getAIResponse(message);
}
function scrollToBottom(element) {
setTimeout(() => {
element.scrollTop = element.scrollHeight;
}, 100);
}
chatWidget.addEventListener('click', function() {
if (chatWindow) {
chatWindow.remove();
chatWindow = null;
return;
}
chatWindow = document.createElement('div');
chatWindow.className = 'fixed bottom-24 right-4 w-80 bg-gray-50 rounded-lg shadow-xl';
chatWindow.innerHTML = `
<div class="bg-white rounded-t-lg border-b p-4">
<div class="flex justify-between items-center">
<div class="flex items-center gap-2">
<div class="w-3 h-3 bg-green-500 rounded-full"></div>
<h3 class="text-lg font-semibold">Chat with Us</h3>
</div>
<button class="text-gray-500 hover:text-gray-700" id="closeChatBtn">
<i class="ri-close-line text-xl"></i>
</button>
</div>
</div>
<div id="chatMessages" class="h-80 overflow-y-auto p-4 space-y-4">
<div class="flex justify-start mb-3">
<div class="bg-white border rounded-lg px-4 py-2 max-w-[80%] shadow-sm">
<p class="text-sm">Hello! How can I help you today?</p>
</div>
</div>
</div>
<div class="bg-white rounded-b-lg border-t p-4">
<form id="chatForm" class="flex gap-2">
<input type="text" id="chatInput" class="flex-1 px-3 py-2 border border-gray-300 rounded-md text-sm" placeholder="Type your message..." required>
<button type="submit" class="px-4 py-2 bg-primary text-white rounded-md hover:bg-primary/90 flex items-center justify-center">
<i class="ri-send-plane-fill"></i>
</button>
</form>
<div class="mt-2 flex gap-2 overflow-x-auto py-1">
<button type="button" class="quick-reply-btn text-xs text-primary bg-primary/10 px-3 py-1 rounded-full whitespace-nowrap hover:bg-primary/20 transition-all duration-300 transform hover:scale-110 active:scale-95">Heart Health</button>
<button type="button" class="quick-reply-btn text-xs text-primary bg-primary/10 px-3 py-1 rounded-full whitespace-nowrap hover:bg-primary/20 transition-all duration-300 transform hover:scale-110 active:scale-95">Mental Health</button>
<button type="button" class="quick-reply-btn text-xs text-primary bg-primary/10 px-3 py-1 rounded-full whitespace-nowrap hover:bg-primary/20 transition-all duration-300 transform hover:scale-110 active:scale-95">Diabetes</button>
<button type="button" class="quick-reply-btn text-xs text-primary bg-primary/10 px-3 py-1 rounded-full whitespace-nowrap hover:bg-primary/20 transition-all duration-300 transform hover:scale-110 active:scale-95">COVID-19</button>
<button type="button" class="quick-reply-btn text-xs text-primary bg-primary/10 px-3 py-1 rounded-full whitespace-nowrap hover:bg-primary/20 transition-all duration-300 transform hover:scale-110 active:scale-95">Nutrition</button>
<button type="button" class="quick-reply-btn text-xs text-primary bg-primary/10 px-3 py-1 rounded-full whitespace-nowrap hover:bg-primary/20 transition-all duration-300 transform hover:scale-110 active:scale-95">Book Appointment</button>
</div>
</div>
`;
document.body.appendChild(chatWindow);
const chatMessages = document.getElementById('chatMessages');
const chatForm = document.getElementById('chatForm');
const chatInput = document.getElementById('chatInput');
const closeChatBtn = document.getElementById('closeChatBtn');
const quickReplyBtns = document.querySelectorAll('.quick-reply-btn');
function closeChat() {
chatWindow.remove();
chatWindow = null;
}
function handleMessage(message, isUser = true) {
if (!message.trim()) return;
const messageElement = createChatMessage(message, isUser);
chatMessages.appendChild(messageElement);
scrollToBottom(chatMessages);
if (isUser) {
const typingIndicator = document.createElement('div');
typingIndicator.className = 'flex justify-start mb-3';
typingIndicator.innerHTML = `
<div class="bg-white border rounded-lg px-4 py-2 max-w-[80%] shadow-sm">
<div class="flex items-center gap-1">
<div class="w-2 h-2 bg-gray-400 rounded-full animate-bounce"></div>
<div class="w-2 h-2 bg-gray-400 rounded-full animate-bounce" style="animation-delay: 0.2s"></div>
<div class="w-2 h-2 bg-gray-400 rounded-full animate-bounce" style="animation-delay: 0.4s"></div>
</div>
</div>
`;
chatMessages.appendChild(typingIndicator);
scrollToBottom(chatMessages);
setTimeout(() => {
typingIndicator.remove();
const response = getResponse(message);
const responseElement = createChatMessage(response, false);
chatMessages.appendChild(responseElement);
scrollToBottom(chatMessages);
}, 1500);
}
}
chatForm.addEventListener('submit', function(e) {
e.preventDefault();
const message = chatInput.value;
handleMessage(message);
chatInput.value = '';
});
quickReplyBtns.forEach(btn => {
btn.addEventListener('click', function() {
handleMessage(this.textContent);
});
});
closeChatBtn.addEventListener('click', closeChat);
chatInput.focus();
});
});
</script>
<div id="consultationModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
<div class="bg-white rounded-lg p-8 w-[600px] max-h-[90vh] overflow-y-auto relative">
<button onclick="closeConsultationModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700">
<i class="ri-close-line text-xl"></i>
</button>
<h2 class="text-3xl font-['Playfair_Display'] font-bold text-gray-900 mb-6">Book Consultation</h2>
<div class="mb-8">
<div class="flex items-center gap-4 mb-4">
<img id="doctorImage" src="" alt="Doctor" class="w-20 h-20 rounded-full object-cover">
<div>
<h3 id="doctorName" class="text-xl font-semibold"></h3>
<p id="doctorSpecialty" class="text-gray-600"></p>
<div class="flex items-center mt-1">
<i class="ri-star-fill text-yellow-400"></i>
<span id="doctorRating" class="ml-1 text-gray-600"></span>
<span id="doctorReviews" class="ml-1 text-gray-600"></span>
</div>
</div>
</div>
</div>
<form id="consultationForm" class="space-y-4">
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Preferred Date</label>
<input type="date" id="consultDate" class="w-full px-3 py-2 border border-gray-300 rounded-md" required min="">
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Preferred Time</label>
<select id="consultTime" class="w-full px-3 py-2 border border-gray-300 rounded-md" required>
<option value="">Select a time slot</option>
<option value="09:00">09:00 AM</option>
<option value="10:00">10:00 AM</option>
<option value="11:00">11:00 AM</option>
<option value="14:00">02:00 PM</option>
<option value="15:00">03:00 PM</option>
<option value="16:00">04:00 PM</option>
</select>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Consultation Type</label>
<select id="consultType" class="w-full px-3 py-2 border border-gray-300 rounded-md" required>
<option value="">Select consultation type</option>
<option value="video">Video Consultation</option>
<option value="audio">Audio Consultation</option>
<option value="chat">Chat Consultation</option>
</select>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Reason for Consultation</label>
<textarea id="consultReason" class="w-full px-3 py-2 border border-gray-300 rounded-md" rows="3" required></textarea>
</div>
<div>
<label class="block text-sm font-medium text-gray-700 mb-1">Any Previous Medical Records?</label>
<div class="mt-1 flex justify-center px-6 pt-5 pb-6 border-2 border-gray-300 border-dashed rounded-md">
<div class="space-y-1 text-center">
<i class="ri-upload-cloud-2-line text-gray-400 text-3xl"></i>
<div class="flex text-sm text-gray-600">
<label for="file-upload" class="relative cursor-pointer bg-white rounded-md font-medium text-primary hover:text-primary/90">
<span>Upload a file</span>
<input id="file-upload" name="file-upload" type="file" class="sr-only" accept=".pdf,.jpg,.jpeg,.png">
</label>
<p class="pl-1">or drag and drop</p>
</div>
<p class="text-xs text-gray-500">PDF, PNG, JPG up to 10MB</p>
</div>
</div>
</div>
<button type="submit" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">Confirm Booking</button>
</form>
</div>
</div>
<script>
function openConsultationModal(button) {
const modal = document.getElementById('consultationModal');
const doctorName = button.getAttribute('data-doctor');
const specialty = button.getAttribute('data-specialty');
const rating = button.getAttribute('data-rating');
const reviews = button.getAttribute('data-reviews');
document.getElementById('doctorName').textContent = doctorName;
document.getElementById('doctorSpecialty').textContent = specialty;
document.getElementById('doctorRating').textContent = rating;
document.getElementById('doctorReviews').textContent = `(${reviews} reviews)`;
// Set minimum date to today
const today = new Date().toISOString().split('T')[0];
document.getElementById('consultDate').min = today;
// Generate doctor image URL based on name
const imageQuery = `professional headshot of an Indian ${doctorName.includes('Dr.') ? doctorName.split('Dr. ')[1] : doctorName} doctor in white coat, traditional Indian features, natural lighting, clean background, warm and approachable expression`;
document.getElementById('doctorImage').src = `https://readdy.ai/api/search-image?query=${encodeURIComponent(imageQuery)}&width=200&height=200&seq=24&orientation=squarish`;
modal.classList.remove('hidden');
}
function closeConsultationModal() {
document.getElementById('consultationModal').classList.add('hidden');
document.getElementById('consultationForm').reset();
}
document.getElementById('consultationForm').addEventListener('submit', function(e) {
e.preventDefault();
const doctorName = document.getElementById('doctorName').textContent;
const date = document.getElementById('consultDate').value;
const time = document.getElementById('consultTime').value;
const type = document.getElementById('consultType').value;
const successModal = document.createElement('div');
successModal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-[60]';
successModal.innerHTML = `
<div class="bg-white rounded-lg p-6 w-96">
<h3 class="text-xl font-semibold mb-4">Consultation Booked Successfully!</h3>
<p class="text-gray-600 mb-2">Your consultation with ${doctorName} has been scheduled.</p>
<p class="text-gray-600 mb-4">Date: ${date}<br>Time: ${time}<br>Type: ${type} consultation</p>
<p class="text-gray-600 mb-4">You will receive a confirmation email with further details and instructions.</p>
<button onclick="this.parentElement.parentElement.remove(); closeConsultationModal();" class="w-full px-4 py-2 text-white bg-primary hover:bg-primary/90 !rounded-button">OK</button>
</div>
`;
document.body.appendChild(successModal);
});
// File upload preview=
document.getElementById('file-upload').addEventListener('change', function(e) {
const file = e.target.files[0];
if (file) {
const fileName = file.name;
const fileSize = (file.size / 1024 / 1024).toFixed(2); // Convert to MB
const preview = document.createElement('div');
preview.className = 'mt-2 text-sm text-gray-500';
preview.innerHTML = `Selected file: ${fileName} (${fileSize} MB)`;
const container = e.target.closest('div');
const existingPreview = container.querySelector('.mt-2');
if (existingPreview) {
existingPreview.remove();
}
container.appendChild(preview);
}
});
</script>
</body>
</html>

