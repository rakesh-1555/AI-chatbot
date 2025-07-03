# Next.js LangChain AI Chatbot

A modern AI chatbot application built with **Next.js 14**, **LangChain**, and **Google Gemini AI**. This project demonstrates how to integrate LangChain with Google's Gemini 2.0 Flash model to create an interactive conversational AI interface.

## 🚀 Features

- **Modern UI**: Clean, responsive chat interface built with React and Tailwind CSS
- **Google Gemini AI**: Powered by Google's latest Gemini 2.0 Flash model
- **LangChain Integration**: Advanced conversation handling with memory and context
- **Real-time Chat**: Interactive messaging with loading states
- **TypeScript**: Fully typed for better development experience
- **Server Actions**: Utilizes Next.js 14 server actions for secure API calls
- **Memory Management**: Conversation history maintained throughout the session

## 🛠️ Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **AI Framework**: LangChain
- **AI Model**: Google Gemini 2.0 Flash
- **Styling**: Tailwind CSS
- **UI Components**: Custom React components with Radix UI icons
- **Environment**: dotenv for configuration management

## 📋 Prerequisites

Before you begin, ensure you have:

- Node.js 18+ installed
- A Google AI Studio account
- Google Gemini API key

## 🚦 Getting Started

### 1. Clone and Install

```bash
# Clone the repository
git clone <repository-url>
cd 15_nextjs_langchain

# Install dependencies
npm install
```

### 2. Environment Setup

1. **Create environment file**:

   ```bash
   cp .env.sample .env
   ```

2. **Get your Google Gemini API key**:

   - Visit [Google AI Studio](https://aistudio.google.com/app/apikey)
   - Create a new API key
   - Copy the key

3. **Configure environment variables**:

   ```env
   # Required: Google Gemini AI API Key
   GOOGLE_GEMINI_KEY=your_google_gemini_api_key_here

   # Optional: OpenAI API Key (for future use)
   # OPENAI_KEY=your_openai_api_key_here

   # Next.js Configuration
   NEXT_PUBLIC_APP_URL=http://localhost:3000
   ```

### 3. Run the Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to see the chatbot in action.

## 🏗️ Project Structure

```
├── actions/
│   └── openai.action.ts      # Server action for AI interactions
├── app/
│   ├── globals.css           # Global styles
│   ├── layout.tsx            # Root layout component
│   └── page.tsx              # Main page component
├── components/
│   └── chat/
│       ├── index.tsx         # Main chat component
│       ├── chat-list.tsx     # Message list component
│       └── chat-bottombar.tsx # Input component
├── public/
│   ├── robot.png            # AI assistant avatar
│   └── user.png             # User avatar
├── .env.sample              # Environment template
├── package.json             # Dependencies and scripts
└── README.md               # Project documentation
```

## 🔧 Available Scripts

```bash
# Development server
npm run dev

# Production build
npm run build

# Start production server
npm run start

# Lint code
npm run lint
```

## 🤖 How It Works

1. **Chat Interface**: Users interact through a clean, modern chat UI
2. **Message Processing**: User messages are sent to the server action
3. **LangChain Pipeline**: Messages are processed through LangChain's conversation chain
4. **AI Generation**: Google Gemini generates contextual responses
5. **Memory Management**: Conversation history is maintained for context
6. **Real-time Updates**: Responses are streamed back to the UI

## 🔌 API Integration

The application uses LangChain's `ChatGoogleGenerativeAI` with the following configuration:

```typescript
const llm = new ChatGoogleGenerativeAI({
  model: "gemini-2.0-flash",
  apiKey: process.env.GOOGLE_GEMINI_KEY,
});
```

### Key Features:

- **Conversation Memory**: Maintains chat history throughout the session
- **System Prompt**: Configured to provide helpful, emoji-free responses
- **Error Handling**: Robust error management for API failures

## 🎨 Customization

### Switching to OpenAI

To use OpenAI instead of Google Gemini:

1. Uncomment the OpenAI import and configuration in `actions/openai.action.ts`
2. Comment out the Google Gemini configuration
3. Add your OpenAI API key to the `.env` file

### Styling

The project uses Tailwind CSS. Customize the appearance by:

- Modifying component styles in the `components/` directory
- Updating the global styles in `app/globals.css`
- Adjusting the Tailwind configuration in `tailwind.config.ts`

## 🔒 Security Notes

- API keys are handled securely through environment variables
- Server actions ensure API calls are made server-side
- No sensitive data is exposed to the client

## 🐛 Troubleshooting

### Common Issues:

1. **API Key Error**: Ensure your Google Gemini API key is correctly set in `.env`
2. **Import Errors**: Run `npm install` to ensure all dependencies are installed
3. **Build Errors**: Check TypeScript errors with `npm run lint`

### Environment Variables Not Loading:

- Ensure `.env` file is in the root directory
- Restart the development server after changing environment variables
- Check that variable names match exactly (case-sensitive)

## 📖 Learn More

- [Next.js Documentation](https://nextjs.org/docs)
- [LangChain Documentation](https://docs.langchain.com/)
- [Google AI Studio](https://aistudio.google.com/)
- [Tailwind CSS](https://tailwindcss.com/docs)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

**Happy Coding! 🚀**

Built with ❤️ using Next.js and LangChain
