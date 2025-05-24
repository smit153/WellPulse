# WellPulse Healthcare Management System

A comprehensive healthcare patient management application that allows patients to easily register, book, and manage their appointments with doctors, featuring administrative tools for scheduling, confirming, and canceling appointments, along with SMS notifications.

## Tech Stack

- Next.js
- Appwrite
- TypeScript
- TailwindCSS
- ShadCN

## Features

- **Patient Registration**: Complete patient profile management with detailed medical history
- **Appointment Management**: Book, reschedule, and cancel appointments
- **Doctor Management**: View and manage doctor profiles and schedules
- **Admin Dashboard**: Comprehensive administrative tools for managing the healthcare system
- **File Upload**: Secure document storage for patient records

## Environment Setup

Create a `.env.local` file in the root directory with the following variables:

```env
# Appwrite Configuration
NEXT_PUBLIC_ENDPOINT=https://cloud.appwrite.io/v1
PROJECT_ID=
API_KEY=
DATABASE_ID=
PATIENT_COLLECTION_ID=
APPOINTMENT_COLLECTION_ID=
NEXT_PUBLIC_BUCKET_ID=

# Admin Access
NEXT_PUBLIC_ADMIN_PASSKEY=

```

For detailed setup instructions, refer to [ENV_SETUP.md](./ENV_SETUP.md)

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/yourusername/healthcare.git
cd healthcare
```

2. Install dependencies:

```bash
npm install
```

3. Set up environment variables (see above)

4. Run the development server:

```bash
npm run dev
```

5. Open [http://localhost:3000](http://localhost:3000) in your browser

## Appointment Workflow

1. **Patient Registration**

   - Complete patient profile with medical history
   - Upload identification documents
   - Provide insurance information

2. **Booking Appointment**

   - Select preferred doctor
   - Choose available time slot
   - Provide appointment reason
   - Add any additional notes

3. **Appointment Management**

   - View upcoming appointments
   - Reschedule if needed
   - Cancel appointments
   - Receive SMS notifications

4. **Admin Functions**
   - View all appointments
   - Confirm/cancel appointments
   - Manage doctor schedules
   - Send appointment notifications

## Security Features

- Secure file uploads
- Encrypted data storage
- Protected admin routes
- Privacy consent management
- Secure API key handling

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## Credentials for testing

- username: John Doe
- email: johndoe1@gmail.com
- phone: +1 858 585 8585

- admin passcode: 123456

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, join our Discord community or open an issue in the repository.
