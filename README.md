# CertiMint - Academic Certificate NFT Platform

**CertiMint** is a comprehensive blockchain-based platform that validates academic assignments using AI-powered analysis and mints verified certificates as NFTs. The platform combines advanced plagiarism detection, AI-generated content detection, and subject relevance validation with blockchain technology to create tamper-proof academic certificates.

## 🎥 Demo

https://github.com/user-attachments/assets/9118c6e1-07c9-4d78-b6a2-9eeec751d131

## 🚀 Vision

The goal of **CertiMint** was to make digital certificates **tamper-proof**, **verifiable**, and **easily accessible** — even for non-crypto users — by blending **web3 security** with **web2 simplicity**.

However, during various hackathons, questions were raised about **scalability** and **feasibility**, which led to a deeper architectural rethink and the following proposed improvements.

## 🌟 Overview

CertiMint is a full-stack solution consisting of three main components:

### 1. **AI Analysis Engine** 
- Advanced plagiarism detection using multiple algorithms
- AI-generated content detection with pattern recognition
- Subject relevance validation using NLP and keyword analysis
- Secure sandbox environment for isolated processing
- OCR processing for PDF documents
-reasoning is given using open source model phi 2

### 2. **Blockchain NFT System**
- Smart contracts written in Vyper for zkSync Sepolia testnet
- ERC-721 compliant NFT certificates
- Immutable certificate storage on blockchain
- SVG-based certificate generation with metadata

### 3. **Web Platform**
- React.js frontend with Web3 integration
- Express.js backend with MongoDB integration
- Real-time assignment tracking and notifications
- Wallet integration (MetaMask) for certificate minting
- Certificate dashboard for viewing and managing NFTs

## 🏗️ System Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │    Backend      │    │  AI Engine+ phi2     │
│   (React.js)    │◄──►│  (Express.js)   │◄──►│  (Python)      │
│                 │    │   + MongoDB     │    │                 │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│  Web3 Wallet    │    │   Cloudinary    │    │   Wikipedia     │
│  (MetaMask)     │    │   (File Store)  │    │   Scraper       │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │
         ▼
┌─────────────────┐
│  zkSync Smart  │
│   Contract      │
│   (Vyper)       │
└─────────────────┘
```

### Processing Flow:
1. **Data Collection Phase**: Web scraping for reference content (Wikipedia)
2. **Analysis Phase**: OCR extraction, plagiarism detection, AI content validation (Sandboxed)
3. **Validation Phase**: Subject relevance checking and integrity scoring
4. **Certification Phase**: NFT minting on zkSync blockchain with certificate metadata

## 🔍 AI-Powered Validation Features

### Advanced Plagiarism Detection
- **Multi-layered detection**: Combines semantic similarity, LLM assessment, and pattern recognition
- **Enhanced algorithms**: Uses transformer models and n-gram analysis
- **Source comparison**: Cross-references with Wikipedia and academic databases
- **Strict thresholds**: Semantic similarity > 40% triggers failure

### AI-Generated Content Detection
- **Pattern Recognition**: Identifies common AI-generated text patterns:
  - Self-references ("As an AI language model...")
  - Formulaic structures (pros/cons, numbered points)
  - Awkward or repetitive phrasing
  - Balanced perspectives ("on one hand... on the other hand")
  - Uniform paragraph structure
- **Emoji Detection**: Any emoji triggers immediate failure
- **Confidence Scoring**: AI confidence > 35% triggers failure
- **LLM Integration**: Uses Phi-2 model for advanced analysis

### Subject Relevance Validation
- **Keyword Analysis**: Deep analysis of subject-specific terminology
- **Content Matching**: Validates alignment between declared and actual content
- **Mismatch Detection**: Identifies subject-content discrepancies
- **Confidence Scoring**: Relevance score must exceed 35% threshold

## 🔐 Blockchain & NFT Features

### Smart Contract (Vyper)
- **ERC-721 Compliant**: Standard NFT implementation
- **zkSync Sepolia**: Deployed on Layer 2 for lower gas costs
- **Contract Address**: `0x5497D3d6aE886f709a7427B1f7f8DE0A2c715bCC`
- **Metadata Storage**: On-chain storage of certificate data
- **Access Control**: Owner-based minting permissions

### Certificate NFTs
- **SVG Generation**: Dynamic certificate creation with personalized data
- **Immutable Records**: Blockchain-secured certificate validation
- **Metadata Structure**:
  ```json
  {
    "Subject": "Computer Science",
    "Course": "Blockchain Development", 
    "image": "data:image/svg+xml;base64,..."
  }
  ```
- **Verification**: Public verification through blockchain explorer

## 🖥️ Frontend Features

### React.js Application
- **Modern UI/UX**: Responsive design with real-time updates
- **Web3 Integration**: MetaMask wallet connection
- **Assignment Tracking**: Progress monitoring and notifications
- **Certificate Dashboard**: View, filter, and manage NFT certificates

### Key Components
- **Upload Interface**: Assignment submission with validation
- **NFT Dashboard**: Certificate viewing and management
- **Wallet Integration**: Seamless Web3 connectivity
- **Progress Tracking**: Real-time validation status

## 🛠️ Technology Stack

### Frontend
- **React.js** - Modern UI framework
- **Viem** - TypeScript Web3 library
- **React Router** - Client-side routing
- **Socket.IO** - Real-time communication
- **SASS** - Advanced CSS preprocessing

### Backend
- **Node.js & Express.js** - RESTful API server
- **MongoDB** - Assignment and user data storage
- **Cloudinary** - File upload and storage
- **Socket.IO** - WebSocket communication
- **CORS** - Cross-origin resource sharing

### AI Engine
- **Python** - Core processing language
- **Transformers** - HuggingFace model integration
- **PaddleOCR** - Optical character recognition
- **NLTK/spaCy** - Natural language processing
- **Docker** - Containerized sandbox environment

### Blockchain
- **Vyper** - Smart contract language
- **zkSync Sepolia** - Layer 2 testnet
- **Moccasin** - Development framework
- **Web3 Libraries** - Blockchain interaction

## 🚀 Installation & Setup

### Prerequisites
- **Node.js** (v16 or higher)
- **Python** (3.8 or higher)
- **Git**
- **MetaMask** browser extension
- **MongoDB** (local or cloud)

### 1. Clone Repository
```bash
git clone https://github.com/Rickyy-Sam07/CertiMint-Engine.git
cd CertiMint-Engine
```

### 2. Backend Setup
```bash
cd server
npm install

# Create .env file with:
# MONGODB_URI=your_mongodb_connection_string
# CLOUDINARY_CLOUD_NAME=your_cloudinary_name
# CLOUDINARY_API_KEY=your_cloudinary_key
# CLOUDINARY_API_SECRET=your_cloudinary_secret

npm start
```

### 3. Frontend Setup
```bash
cd client
npm install
npm run dev
```

### 4. AI Engine Setup
```bash
cd AI_analysis_engine
pip install -r requirements.txt

# Download OCR models
python download_ocr_models.py

# Download Phi-2 LLM model (optional)
wget https://huggingface.co/TheBloke/phi-2-GGUF/resolve/main/phi-2.Q4_K_M.gguf -O phi-2.Q4_K_M.gguf
```

### 5. Blockchain Setup (Optional)
```bash
cd NFT_part
pip install moccasin

# Configure networks in moccasin.toml
# Deploy contract (if needed)
moccasin run deploy
```

## 📖 Usage Guide

### For Students

1. **Connect Wallet**
   - Install MetaMask extension
   - Connect to zkSync Sepolia testnet
   - Get test ETH from faucet

2. **Submit Assignment**
   - Upload PDF document
   - Specify subject area
   - Monitor validation progress
   - Wait for AI analysis completion

3. **Mint Certificate**
   - Complete all validation steps
   - Ensure wallet is connected
   - Click "Mint Certificate"
   - Confirm blockchain transaction

4. **View Certificates**
   - Access NFT Dashboard
   - View certificate collection
   - Share or verify certificates

### For Developers

#### Running AI Analysis
```bash
cd AI_analysis_engine

# Basic analysis
python main.py --file data/assignment.pdf --subject "Computer Science" --id ASG001

# With enhanced detection
python enhanced_detection.py --file data/assignment.pdf --subject "Machine Learning"

# Using Docker sandbox
docker build -t certimint-ai .
docker run --network=none -v $(pwd)/data:/app/data certimint-ai
```

#### Smart Contract Interaction
```bash
cd NFT_part

# Deploy new contract
moccasin run deploy

# Mint NFT certificate
moccasin run mint_nft

# Verify contract on explorer
moccasin verify --contract-address 0x... --network zksync-sepolia
```

#### API Endpoints
```bash
# Backend API endpoints
GET    /api/assignments          # Get all assignments
POST   /api/upload               # Upload assignment
GET    /api/assignments/:id      # Get specific assignment
POST   /api/validate             # Trigger AI validation
GET    /api/reviewed/:userId     # Get user's reviewed assignments
```

## 🔧 Configuration

### Environment Variables

#### Frontend (.env)
```env
VITE_API_URL=http://localhost:3900
VITE_SOCKET_URL=http://localhost:3900
VITE_CONTRACT_ADDRESS=0x5497D3d6aE886f709a7427B1f7f8DE0A2c715bCC
```

#### Backend (.env)
```env
MONGODB_URI=mongodb+srv://...
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
PORT=3900
```

#### AI Engine
```env
TRANSFORMERS_OFFLINE=1
HF_HUB_OFFLINE=1
SANDBOX_MODE=true
MODEL_PATH=./phi-2.Q4_K_M.gguf
```

### Network Configuration
The platform is configured for **zkSync Sepolia testnet**:
- **Chain ID**: 300
- **RPC URL**: https://sepolia.era.zksync.dev
- **Explorer**: https://sepolia.explorer.zksync.io
- **Faucet**: https://faucet.zksync.io

## 🔒 Security & Sandbox

### Network Isolation
The AI analysis engine implements multiple security layers:

1. **Docker Isolation**: Complete network isolation with `--network=none`
2. **Environment Controls**: Offline mode enforcement for ML libraries
3. **Process Monitoring**: Active network activity detection
4. **Verification Checks**: Startup isolation validation

### Sandbox Environment
```bash
# Production deployment with network isolation
docker build -t certimint-sandbox .
docker run --network=none \
  -v $(pwd)/data:/app/data \
  -v $(pwd)/models:/app/models \
  certimint-sandbox python main.py \
  --file data/assignment.pdf \
  --subject "Computer Science"
```

### Security Alerts
- Immediate warnings for isolation breaches
- Network activity monitoring with tcpdump
- Clear security status indicators

## 📊 Validation Results

### Analysis Output
```json
{
  "subject": "Computer Science",
  "assignment_id": "ASG12345",
  "validation_timestamp": "2024-10-15T14:30:22.123456",
  "plagiarism_check": {
    "status": "checked",
    "plagiarism_percentage": 18.5,
    "llm_similarity": 15.2,
    "emoji_detected": false,
    "ai_patterns_detected": false,
    "similar_sources": [...]
  },
  "content_validation": {
    "status": "PASSED",
    "relevance_score": 87,
    "subject_match": true,
    "comments": "Content is highly relevant to Computer Science"
  },
  "ai_detection": {
    "ai_patterns_detected": false,
    "ai_confidence": 12.5,
    "patterns": []
  },
  "status": "PASSED",
  "sandbox_mode": true
}
```

### Pass/Fail Criteria
- ✅ **PASS**: Plagiarism < 40%, No AI patterns, Relevance > 35%, No emojis
- ❌ **FAIL**: High plagiarism, AI patterns detected, Subject mismatch, Emojis present

## 🎯 Project Structure

```
CertiMint/
├── client/                     # React.js Frontend
│   ├── src/
│   │   ├── pages/             # Main application pages
│   │   ├── components/        # Reusable components
│   │   ├── services/          # Web3 and API services
│   │   └── utils/             # Utilities and constants
│   └── package.json
├── server/                     # Express.js Backend  
│   ├── server.js              # Main server file
│   ├── cloudinary.js          # File upload config
│   └── package.json
├── AI_analysis_engine/         # Python AI Engine
│   ├── main.py                # Core analysis logic
│   ├── ocr_processor.py       # PDF text extraction
│   ├── enhanced_detection.py  # Advanced AI detection
│   ├── llm_sandbox.py         # Sandboxed LLM processing
│   ├── plagiarism_algorithms.py # Plagiarism detection
│   ├── web_scraper.py         # Wikipedia reference collection
│   └── requirements.txt
├── NFT_part/                   # Blockchain Components
│   ├── src/
│   │   └── mint_certificate2.vy # Smart contract
│   ├── deploy.py              # Deployment script
│   ├── mint_nft.py           # NFT minting script
│   └── moccasin.toml         # Blockchain config
└── docker/                    # Docker configurations
```

## 🐛 Troubleshooting

### Common Issues

#### Wallet Connection Issues
```bash
# Ensure MetaMask is installed and connected to zkSync Sepolia
# Check network configuration in wallet settings
```

#### AI Analysis Failures
```bash
# Check Python dependencies
pip install -r AI_analysis_engine/requirements.txt

# Verify model files exist
ls -la AI_analysis_engine/*.gguf

# Check Docker isolation
docker ps --filter "network=none"
```

#### Smart Contract Errors
```bash
# Verify contract deployment
moccasin run deploy --network zksync-sepolia

# Check contract address in constants.js
# Ensure sufficient testnet ETH balance
```

## 🧩 Proposed Scalability & Feasibility Enhancements

### 🏗️ Smart Contract Architecture

- **Contract Factory Pattern** — for dynamic deployment and lifecycle management of per-user or per-institution contracts.  
- **Minimal Proxies (Clones)** — to reduce deployment costs using the [EIP-1167](https://eips.ethereum.org/EIPS/eip-1167) standard.  
- **Batch Minting** — institutions can mint multiple NFTs in a single transaction, optimizing gas and network efficiency.  

---

### 💡 Wallet & User Experience

- **Smart Wallets + Social Login (Abstracted Wallets)** — enabling seamless onboarding for non-crypto users.  
- **zkSync Paymaster Integration** — to enable gasless transactions and sponsor minting fees for smoother UX.  

---

## ⚡ Blockchain & Network Choices

### For **Public zkSync Chain**

- NFTs are valid for **10 years**, requiring **renewal thereafter** (limitation).  
- Currently, a **single contract architecture** with **GraphQL-based frontend fetching** works fine.  
- Can evolve to **minimal contract clones** per user/institution for **modularity** and **horizontal scalability** (recommended long-term approach).  
- **Batch Minting** and **Smart Wallet + Social Login** are under implementation.  
- **Polygon Chain** offers **cheaper gas** and **permanent storage**, though with **security trade-offs**.  

---

### For **Private L2 Chains (e.g. custom zkRollup)**

- Enables **custom fee control**, **enhanced privacy**, and **configurable scalability**.  
- Certificates remain **private**, while **proofs can be anchored on public chains** for transparency and verifiability.  

---

## 📊 Data Layer

- **Indexing via The Graph or zkIndex** for efficient NFT data retrieval and filtering.  
- **Super-fast Frontend Performance** for a seamless user experience.
  
---
## 💭 Personal Note

I eventually paused work on **CertiMint** after someone mentioned that *“no one cares about certificates these days.”*  
While I partly understand that perspective, I still believe **verifiable digital credentials** have huge potential — especially in **education**, **hiring**, and **identity systems**.

If you find this concept interesting, feel free to **fork**, **build upon**, or **collaborate** on the improvements listed above.  
There’s plenty of unexplored potential here — especially around **wallet abstraction**, **modular contract scaling**, and **zk-enabled privacy**.

## 🤝 Contributing

Contributions, ideas, and discussions are welcome!  
You can help by:

- Implementing **Minimal Proxy Factories**  
- Building **zkSync Paymaster integrations**  
- Improving **UI/UX for Web2 onboarding**  
- Creating **Private L2 Rollup prototypes**

---

## 📜 License

This project is licensed under the **MIT License** — free for personal and commercial use.

## 🎖️ Acknowledgments

- **OpenAI** - GPT models for AI detection research
- **HuggingFace** - Transformer models and tokenizers  
- **zkSync** - Layer 2 scaling solution
- **PaddleOCR** - Optical character recognition
- **Wikipedia** - Reference data source
- **Snekmate** - Vyper contract libraries

---

**Built with ❤️ **

*Securing academic integrity through blockchain technology and AI-powered validation.*
