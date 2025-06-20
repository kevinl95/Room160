# Room160: SMS Homework Help for Every Student

## Why Room160?

Many students struggle with homework at home but lack reliable internet access to get help online. However, most families have access to basic cell phones with SMS texting. Room160 bridges this gap by letting students text their homework questions and receive immediate help - either from AI or directly from you, their teacher, from your email inbox. You will get a special number you can give families and respond from your school email, making it easy to protect your privacy and your off time while providing a high-quality resource for your students.

**The Problem We Solve:**
- Students need homework help but don't have internet at home
- Giving out your phone number is a privacy and work/life balance nightmare
- Traditional tutoring isn't available 24/7
- Teachers want to help but can't be available around the clock
- Parents may not be able to help with advanced coursework

**How Room160 Helps:**
- Students text questions to a dedicated phone number
- AI provides instant, educational responses for most questions
- All interactions with you occur via your school email, making it easy to disengage, flag content for administration, and preserve your privacy.
- Works with any basic cell phone - no smartphone or internet required for your students

**What does Room160 mean?**
SMS messages are capped at 160 characters, so the project name is a playful reference to this underlying technology. Room160 will send multi-part responses, however, so you don't need to worry about message length limits!

## How It Works

1. **Student texts a question** to your Room160 phone number
2. **Messages are routed**
   - Messages starting with "@teacher" → Go directly to your email
   - Questions and queries can be answered by AI. A student-friendly Claude 3 agent is deployed to Amazon Bedrock for general student help and questions.
3. **You stay in control** - receive email notifications and can disable AI anytime

## Getting Started

### Step 1: Deploy Room160 to AWS

Click the "Launch Stack" button below to set up Room160 in your AWS account:

[🚀 **Launch Room160 Stack**](s3-link-coming-soon)

**You'll need to provide:**
- **Your email address** - Where student messages will be forwarded
- **AI Mode** - Choose "Enable" for AI assistance or "Disable" for teacher-only mode

**Cost:** Approximately $5-15/month depending on usage (AWS charges for AI responses and SMS)

### Step 2: Get Your SMS Phone Number

After deployment, you'll need a phone number for students to text:

1. **Sign up for Twilio** (recommended SMS provider)
   - Go to [twilio.com](https://twilio.com)
   - Create a free account
   - Purchase a phone number (~$1/month)

2. **Connect Twilio to Room160**
   - In your Twilio console, find "Webhooks" settings
   - Copy the "SMSWebhookURL" from your AWS deployment
   - Paste it as your webhook URL in Twilio

### Step 3: Share with Students

Give students your new SMS number and these simple instructions:

**"Text your homework questions to [YOUR-NUMBER]. For urgent questions or if you need to reach me directly, start your message with @teacher"**

## Student Examples

**Math Help:**
- Student: "What is 2x + 5 = 15?"
- AI: "To solve 2x + 5 = 15: Subtract 5 from both sides: 2x = 10. Divide by 2: x = 5. Check: 2(5) + 5 = 15 ✓"

**Direct to Teacher:**
- Student: "@teacher I'm confused about the essay assignment"
- System: Forwards message to your email immediately

**Science Question:**
- Student: "Why do leaves change color?"
- AI: "Leaves change color in fall because they stop making green chlorophyll. This reveals other colors like yellow and red that were always there but hidden by the green."

## Safety Features

- **Content filtering** - AI won't respond to inappropriate messages
- **Teacher override** - Students can always reach you directly with "@teacher"
- **No personal data** - Students only need to know the SMS number
- **Audit trail** - Messages to you are received at you school email

## Managing Your Room160

### Disable AI Temporarily
If you want all messages to come to you instead of AI:
1. Go to your AWS CloudFormation console
2. Update your stack
3. Change "EnableAI" to "false"

### Cost Management
- AI responses cost ~$0.01-0.05 each
- SMS messages cost ~$0.0075 each
- Set up AWS billing alerts to monitor spending

## Troubleshooting

**Students aren't getting responses:**
- Check that Twilio webhook is configured correctly
- Verify your AWS deployment completed successfully

**High costs:**
- Set usage limits in AWS
- Consider disabling AI during non-homework hours
- Monitor which types of questions generate the most AI usage

## Support

Room160 is designed to be simple and reliable. Most issues can be resolved by:
1. Checking your Twilio webhook configuration
2. Verifying your email address in AWS
3. Ensuring your AWS deployment completed successfully

For technical support, check the AWS CloudFormation console for any error messages.

---

**Room160: Making homework help accessible to every student, regardless of their internet access at home.**