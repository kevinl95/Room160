# Room160: SMS Homework Help for Every Student

[![Lint CloudFormation Template](https://github.com/kevinl95/Room160/actions/workflows/main.yml/badge.svg)](https://github.com/kevinl95/Room160/actions/workflows/main.yml)

## Why Room160?

Many students struggle with homework at home but lack reliable internet access to get help online. However, most families have access to basic cell phones with SMS texting. Room160 bridges this gap by letting students text their homework questions and receive immediate help - either from AI or directly from you, their teacher, from your email inbox. You will get a special number you can give families and respond from your school email, making it easy to protect your privacy and your off time while providing a high-quality resource for your students.

**The Problem We Solve:**
- Students need homework help but don't have internet at home
- Giving out your phone number is a privacy and work/life balance nightmare
- Traditional tutoring isn't available 24/7
- Teachers want to help but can't be available around the clock
- Parents may not be able to help with advanced coursework

**How Room160 Helps:**
- Students text homework questions to get instant AI help or reach you directly
- AI provides immediate, educational responses for most questions
- You receive email notifications when students need your help
- **Important:** You respond by texting students directly (not by replying to emails)
- Works with any basic cell phone - no smartphone or internet required for your students

**What does Room160 mean?**

SMS messages are capped at 160 characters, so the project name is a playful reference to this underlying technology. Room160 will send multi-part responses, however, so you don't need to worry about message length limits!

## How It Works

1. **Student texts a question** to your Room160 phone number
2. **Messages are routed**
   - Messages starting with "@teacher" → You get email notification with student's phone number
   - Other questions → AI responds automatically via SMS
3. **You respond via SMS** - Email notifications include the student's phone number for you to text back directly
4. **You stay in control** - Receive email alerts and can disable AI anytime

## Getting Started

### Step 1: Deploy Room160 to AWS

Click the "Launch Stack" button below to set up Room160 in your AWS account:

[🚀 **Launch Room160 Stack**](s3-link-coming-soon)

**You'll need to provide:**
- **Your email address** - Where student messages will be forwarded
- **AI Mode** - Choose "Enable" for AI assistance or "Disable" for teacher-only mode
- **TextBelt API Key** - Simple SMS service (get free key at [textbelt.com](https://textbelt.com))

**Cost:** Approximately $2-8/month depending on usage (AWS charges + TextBelt SMS costs)

**AI Technology:** Uses Claude 3 Haiku for fast, cost-effective student responses

### Step 2: Get Your TextBelt API Key

1. **Sign up for TextBelt**
   - Go to [textbelt.com](https://textbelt.com)
   - Create a free account (no business verification required!)
   - Get your API key from the dashboard
   - Much simpler than traditional SMS providers

2. **Add API Key to Room160**
   - Your API key was entered during CloudFormation deployment
   - TextBelt handles all SMS routing automatically
   - No phone numbers to buy or configure!

### Step 3: Enroll Your Students

1. **Visit Your Enrollment Page**
   - Find the "EnrollmentURL" in your CloudFormation outputs
   - Click the link to open the student enrollment form

2. **Add Student Phone Numbers**
   - Copy/paste student phone numbers into the form
   - Use any format: 555-123-4567, (555) 123-4567, or 5551234567
   - One number per line

3. **Click "Enroll Students"**
   - Students automatically receive welcome messages
   - They can immediately start texting homework questions!

**Student Instructions:**
*"You've been enrolled in Room160! Text your homework questions to get instant help. Start your message with @teacher to reach me directly."*

## Student Examples

**Math Help:**
- Student: "What is 2x + 5 = 15?"
- AI (Claude 3 Haiku): "To solve 2x + 5 = 15: Subtract 5 from both sides: 2x = 10. Divide by 2: x = 5. Check: 2(5) + 5 = 15 ✓"

**Direct to Teacher:**
- Student: "@teacher I'm confused about the essay assignment"
- System: Sends email notification to teacher with student's phone number
- Teacher: Texts student directly at the provided number to help with assignment

**Science Question:**
- Student: "Why do leaves change color?"
- AI (Claude 3 Haiku): "Leaves change color in fall because they stop making green chlorophyll. This reveals other colors like yellow and red that were always there but hidden by the green."

## Safety Features

- **Content filtering** - AI won't respond to inappropriate messages
- **Teacher override** - Students can always reach you directly with "@teacher"
- **Email notifications only** - You get alerts via email but respond via SMS to maintain privacy
- **No personal phone exposure** - Students never see your personal number
- **Audit trail** - All student messages are logged and you're notified via email

## Managing Your Room160

### How Teacher Responses Work
**Important:** Email notifications are one-way alerts only. To respond to students:
1. **Read the email notification** - Contains student's message and phone number
2. **Text the student directly** - Use the phone number provided in the email
3. **Student receives your SMS** - They can continue the conversation via text

### Disable AI Temporarily
If you want all messages to come to you instead of AI:
1. Go to your AWS CloudFormation console
2. Update your stack
3. Change "EnableAI" to "false"
4. **Note:** You'll get email notifications for ALL student messages and need to respond via SMS

### Cost Management
- **AI responses:** ~$0.001-0.003 each (Claude 3 Haiku is very affordable!)
- **SMS messages:** ~$0.0075 each via TextBelt
- **AWS infrastructure:** ~$1-3/month for Lambda, SNS, DynamoDB
- **Total typical cost:** $2-8/month for a classroom of 30 students
- Set up AWS billing alerts to monitor spending

## Troubleshooting

**Students aren't getting responses:**
- Check that your TextBelt API key is valid
- Verify students were properly enrolled through the web form
- Ensure your AWS deployment completed successfully

**Students not receiving welcome messages:**
- Double-check phone number formats in the enrollment form
- Verify TextBelt account has sufficient credits

**High costs:**
- Monitor TextBelt usage in their dashboard
- Set usage limits in AWS
- Consider disabling AI during non-homework hours

## Technical Details

**AI Model:** Claude 3 Haiku by Anthropic
- **Speed:** 2-5 second response times
- **Cost:** ~10x cheaper than GPT-4 or Claude 3 Sonnet
- **Quality:** Excellent for educational content and homework help
- **Safety:** Built-in content filtering and educational focus

**AWS Services Used:**
- **Amazon Bedrock** - AI model hosting
- **AWS Lambda** - Message processing
- **Amazon SNS** - Email notifications
- **Amazon DynamoDB** - Student enrollment storage
- **API Gateway** - Webhook endpoints

## Support

Room160 is designed to be simple and reliable. Most issues can be resolved by:
1. Checking your TextBelt account status and credits
2. Verifying student enrollment through the web interface
3. Ensuring your AWS deployment completed successfully
4. Checking that Claude 3 Haiku is available in your AWS region

For technical support, check the AWS CloudFormation console for any error messages.

---

**Room160: Making homework help accessible to every student, regardless of their internet access at home.**