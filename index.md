<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Student Registration Form</title>
  <!-- Tailwind CSS for clean, modern styling -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Fonts: Inter -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Inter', sans-serif;
    }
  </style>
</head>
<body class="bg-slate-100 min-h-screen flex items-center justify-center p-4 sm:p-6">

  <!-- Main Card Container -->
  <div class="w-full max-w-md bg-white rounded-2xl shadow-xl border border-slate-100 p-6 sm:p-8 transition-all">
    
    <!-- Header -->
    <div class="text-center mb-8">
      <div class="inline-flex items-center justify-center w-12 h-12 rounded-xl bg-blue-100 text-blue-600 mb-3">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l9-5-9-5-9 5 9 5z" />
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0112 20.055a11.952 11.952 0 01-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z" />
        </svg>
      </div>
      <h1 class="text-2xl font-bold text-slate-800">Student Registration</h1>
      <p class="text-sm text-slate-500 mt-1">Please fill out the details below to complete your enrollment.</p>
    </div>

    <!-- Success Message Alert (Hidden by default) -->
    <div id="successBanner" class="hidden mb-6 p-4 rounded-xl bg-emerald-50 border border-emerald-200 text-emerald-800 flex items-start space-x-3">
      <svg class="w-5 h-5 text-emerald-600 mt-0.5 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
      </svg>
      <div>
        <p class="font-semibold text-sm">Registration Successful!</p>
        <p class="text-xs text-emerald-700 mt-0.5">The student details have been recorded successfully.</p>
      </div>
    </div>

    <!-- Registration Form -->
    <form id="registrationForm" class="space-y-5" action="#" method="POST" novalidate>
      
      <!-- 1. Full Name -->
      <div>
        <label for="fullName" class="block text-sm font-semibold text-slate-700 mb-1">Full Name <span class="text-rose-500">*</span></label>
        <input 
          type="text" 
          id="fullName" 
          name="fullName" 
          required 
          placeholder="e.g. Jane Doe"
          class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-blue-500 focus:border-blue-500 text-slate-800 outline-none transition text-sm"
        >
        <p class="error-text text-xs text-rose-500 mt-1 hidden" id="fullNameError">Please enter a valid full name.</p>
      </div>

      <!-- 2. Email Address -->
      <div>
        <label for="email" class="block text-sm font-semibold text-slate-700 mb-1">Email Address <span class="text-rose-500">*</span></label>
        <input 
          type="email" 
          id="email" 
          name="email" 
          required 
          placeholder="jane.doe@example.com"
          class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-blue-500 focus:border-blue-500 text-slate-800 outline-none transition text-sm"
        >
        <p class="error-text text-xs text-rose-500 mt-1 hidden" id="emailError">Please enter a valid email address.</p>
      </div>

      <!-- 3. Password -->
      <div>
        <label for="password" class="block text-sm font-semibold text-slate-700 mb-1">Password <span class="text-rose-500">*</span></label>
        <input 
          type="password" 
          id="password" 
          name="password" 
          required 
          placeholder="••••••••"
          class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-blue-500 focus:border-blue-500 text-slate-800 outline-none transition text-sm"
        >
        <p class="error-text text-xs text-rose-500 mt-1 hidden" id="passwordError">Password must be at least 6 characters long.</p>
      </div>

      <!-- 4. Phone Number -->
      <div>
        <label for="phone" class="block text-sm font-semibold text-slate-700 mb-1">Phone Number <span class="text-rose-500">*</span></label>
        <input 
          type="tel" 
          id="phone" 
          name="phone" 
          required 
          placeholder="+1 (555) 000-0000"
          class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-blue-500 focus:border-blue-500 text-slate-800 outline-none transition text-sm"
        >
        <p class="error-text text-xs text-rose-500 mt-1 hidden" id="phoneError">Please enter a valid phone number.</p>
      </div>

      <!-- 5. Age -->
      <div>
        <label for="age" class="block text-sm font-semibold text-slate-700 mb-1">Age <span class="text-rose-500">*</span></label>
        <input 
          type="number" 
          id="age" 
          name="age" 
          required 
          min="1" 
          max="120" 
          placeholder="18"
          class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-blue-500 focus:border-blue-500 text-slate-800 outline-none transition text-sm"
        >
        <p class="error-text text-xs text-rose-500 mt-1 hidden" id="ageError">Please enter an age between 1 and 120.</p>
      </div>

      <!-- Submit Button -->
      <div class="pt-2">
        <button 
          type="submit" 
          class="w-full bg-blue-600 hover:bg-blue-700 active:scale-[0.99] text-white font-semibold py-3 px-4 rounded-xl shadow-md shadow-blue-500/20 transition-all cursor-pointer flex items-center justify-center space-x-2"
        >
          <span>Register Student</span>
          <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
          </svg>
        </button>
      </div>

    </form>
  </div>

  <!-- Interactive JavaScript Validation & Feedback handling -->
  <script>
    document.addEventListener('DOMContentLoaded', () => {
      const form = document.getElementById('registrationForm');
      const successBanner = document.getElementById('successBanner');

      // Fields to validate
      const fields = [
        {
          id: 'fullName',
          errorId: 'fullNameError',
          validate: (val) => val.trim().length >= 2
        },
        {
          id: 'email',
          errorId: 'emailError',
          validate: (val) => /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(val.trim())
        },
        {
          id: 'password',
          errorId: 'passwordError',
          validate: (val) => val.length >= 6
        },
        {
          id: 'phone',
          errorId: 'phoneError',
          validate: (val) => /^[0-9\-\+\s\(\)]{7,15}$/.test(val.trim())
        },
        {
          id: 'age',
          errorId: 'ageError',
          validate: (val) => {
            const num = parseInt(val, 10);
            return !isNaN(num) && num >= 1 && num <= 120;
          }
        }
      ];

      // Inline validation state clearing on typing
      fields.forEach(field => {
        const input = document.getElementById(field.id);
        const errorEl = document.getElementById(field.errorId);

        input.addEventListener('input', () => {
          if (field.validate(input.value)) {
            input.classList.remove('border-rose-500', 'focus:ring-rose-500', 'focus:border-rose-500');
            input.classList.add('border-slate-300', 'focus:ring-blue-500', 'focus:border-blue-500');
            errorEl.classList.add('hidden');
          }
        });
      });

      // Handle form submission
      form.addEventListener('submit', (e) => {
        e.preventDefault();
        let isValid = true;

        fields.forEach(field => {
          const input = document.getElementById(field.id);
          const errorEl = document.getElementById(field.errorId);

          if (!field.validate(input.value)) {
            isValid = false;
            input.classList.remove('border-slate-300', 'focus:ring-blue-500', 'focus:border-blue-500');
            input.classList.add('border-rose-500', 'focus:ring-rose-500', 'focus:border-rose-500');
            errorEl.classList.remove('hidden');
          } else {
            input.classList.remove('border-rose-500', 'focus:ring-rose-500', 'focus:border-rose-500');
            input.classList.add('border-slate-300', 'focus:ring-blue-500', 'focus:border-blue-500');
            errorEl.classList.add('hidden');
          }
        });

        if (isValid) {
          // Display success state
          successBanner.classList.remove('hidden');
          form.reset();

          // Scroll smoothly to top of card if needed
          window.scrollTo({ top: 0, behavior: 'smooth' });

          // Hide banner automatically after 5 seconds
          setTimeout(() => {
            successBanner.classList.add('hidden');
          }, 5000);
        }
      });
    });
  </script>
</body>
</html>