# Environment Variables Setup Guide

This guide will walk you through setting up all the required environment variables for the WellPulse healthcare application.

## Prerequisites

- An Appwrite account (Sign up at [appwrite.io](https://appwrite.io))

## Step 1: Create Appwrite Project

1. Log in to your Appwrite Console
2. Click "Create Project"
3. Name your project
4. Note down your Project ID from the project settings

## Step 2: Set Up Appwrite Database

1. In your Appwrite project, go to "Databases"
2. Click "Create Database"
3. Name it (e.g., "healthcare_db")
4. Note down the Database ID

## Step 3: Create Collections

Create the following collections in your database:

### Patient Collection

1. Go to your database
2. Click "Create Collection"
3. Name it "patients"
4. Note down the Collection ID
5. Add the following attributes:
   - userId (string)
   - name (string)
   - email (string)
   - phone (string)
   - birthDate (datetime)
   - gender (string)
   - address (string)
   - occupation (string)
   - emergencyContactName (string)
   - emergencyContactNumber (string)
   - primaryPhysician (string)
   - insuranceProvider (string)
   - insurancePolicyNumber (string)
   - allergies (string[])
   - currentMedication (string[])
   - familyMedicalHistory (string)
   - pastMedicalHistory (string)
   - identificationType (string)
   - identificationNumber (string)
   - identificationDocument (file)
   - privacyConsent (boolean)

### Appointment Collection

1. Create another collection named "appointments"
2. Note down the Collection ID
3. Add the following attributes:
   - userId (string)
   - patient (string)
   - primaryPhysician (string)
   - schedule (datetime)
   - reason (string)
   - status (string) - enum: ["scheduled", "pending", "cancelled"]
   - note (string)

## Step 4: Create Storage Bucket

1. Go to "Storage" in your Appwrite project
2. Click "Create Bucket"
3. Name it (e.g., "healthcare_files")
4. Note down the Bucket ID
5. Set the following permissions:
   - Read: role:all
   - Write: role:all
   - Delete: role:all

## Step 5: Generate API Key

1. Go to "Settings" → "API Keys"
2. Click "Create API Key"
3. Give it a name (e.g., "API Key")
4. Select the following permissions:
   - databases.read
   - databases.write
   - storage.read
   - storage.write
   - users.read
   - users.write
5. Copy the generated API Key

## Step 6: Create Environment File

1. Create a new file named `.env` in the root of your project
2. Add the following variables with your values:

```env
# Appwrite Configuration
NEXT_PUBLIC_ENDPOINT=https://cloud.appwrite.io/v1
PROJECT_ID=your_project_id
API_KEY=your_api_key
DATABASE_ID=your_database_id
PATIENT_COLLECTION_ID=your_patient_collection_id
APPOINTMENT_COLLECTION_ID=your_appointment_collection_id
NEXT_PUBLIC_BUCKET_ID=your_bucket_id

# Admin Access
NEXT_PUBLIC_ADMIN_PASSKEY=your_secure_passkey

```

Replace the placeholder values with your actual values from the previous steps.

## Step 7: Verify Setup

1. Start your development server:

```bash
npm run dev
```

2. Test the following functionality:
   - Patient registration with all fields
   - Doctor listing
   - Appointment booking with all required fields
   - File uploads for patient documents
   - Admin access with passkey

## Security Notes

- Never commit `.env` to version control
- Keep your API keys secure and don't share them
- Regularly rotate your API keys
- Use strong passkeys for admin access
- Consider using different API keys for development and production
- Ensure proper file upload restrictions in your storage bucket
- Set up proper database indexes for frequently queried fields

## Troubleshooting

If you encounter any issues:

1. Verify all environment variables are correctly set
2. Check Appwrite console for any permission issues
3. Ensure all collection attributes are properly configured with correct types
4. Verify API key permissions
5. Check browser console for any client-side errors
6. Verify file upload permissions in the storage bucket
7. Check if all required fields are properly set in the collections

## Additional Resources

- [Appwrite Documentation](https://appwrite.io/docs)
- [Next.js Environment Variables](https://nextjs.org/docs/basic-features/environment-variables)
