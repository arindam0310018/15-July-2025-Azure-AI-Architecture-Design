# AZURE AI ARCHITECTURE & DESIGN:-

In order to adopt AI based workloads in a consistent and production ready way, __An Azure AI Landing Zone is a MUST.__

| <img src="/Images/1-Banner.jpg"> |
| --------- |

| 📌 WHY AZURE AI LANDING ZONE IS REQUIRED:- |
| --------- |
| 🎯 __Standardization__ - Develop and Promote the use of Blueprint(Predefined Templates) to deploy AI Services. |
| 🎯 __Faster Time to Market__ - Less time on Infrastructure, more focus on building AI solutions. |
| 🎯 __Security__ - Azure Policies, Network Isolation, Use of Managed Identities, RBAC, Encryption at rest/transit, Certificates. |
| 🎯 __Scalability__ - Support onboarding of New AI Uses cases without Re-Architecture. |
| 🎯 __Operational Excellence__ - Implementation of Observability and FinOps. Addtionally for AI Lifecycle Management, DevOps/MLOps working Hand to Hand. |

| 🚀 AGENDA:- |
| --------- |
| __💡Myths of AI Engineering.__ |
| __💡Myths of Data Science.__ |
| __💡Breakdown of AI based on Technology and Implementation.__ |
| __💡Breakdown of AI based on User interactions and Development.__ |
| __💡How All Fits Together.__ |
| __💡Decision Tree.__ |
| __💡Hub and Spoke Model for AI.__ |
| __💡Classical ML Architecture.__ |
| __💡Analytics Platform Architecture.__ |
| __💡Low Code No Code Architecture.__ |
| __💡Importance of MLOps.__ |
| __💡Consumption Model - APIM and MCP.__ |
| __💡How AI Team Structure Looks Like.__ |

| 📌 MYTHS OF AI ENGINEERING:- |
| --------- |
| <img src="/Images/2-Myth-AI-Engineering-1.jpg"> |
| <img src="/Images/3-Myth-AI-Engineering-2.jpg"> |

| 📌 MYTHS OF DATA SCIENCE:- |
| --------- |
| <img src="/Images/4-Myth-Data-Science.jpg"> |

| 📌 BREAKDOWN OF AI BASED ON TECHNOLOGY & IMPLEMENTATION:- |
| --------- |
| __✅ Machine Learning.__|
| __✅ Deep Learning.__|
| __✅ Natural Language Processing.__|

| 📌 BREAKDOWN OF AI BASED ON USER INTERACTIONS & DEVELOPMENT:- |
| --------- |
| __✅ Low Code No Code AI.__|
| __✅ Generative AI.__|
| __✅ Conversational AI.__|

| 📌 HOW ALL FITS TOGETHER:- |
| --------- |
| __📦 Machine Learning in LOW CODE NOT CODE; GEN AI; CONVERSATIONAL AI__ |
| <img src="/Images/5-Classical-Machine-Learning.jpg"> |
| __📦 Deep Learning in LOW CODE NOT CODE; GEN AI; CONVERSATIONAL AI__ |
| <img src="/Images/6-Deep-Learning.jpg"> |
| __📦 Natural Language Processing in LOW CODE NOT CODE; GEN AI; CONVERSATIONAL AI__ |
| <img src="/Images/7-NLP.jpg"> |

| 📌 DECISION TREE:- |
| --------- |
| <img src="/Images/8-AI-Decision-Tree.jpg"> |

| 📌 HUB & SPOKE MODEL FOR AI:- |
| --------- |
| <img src="/Images/10-AI-Architecture -Hub-Spoke.jpg"> |

| 📌 CLASSICAL ML ARCHITECTURE:- |
| --------- |
| <img src="/Images/11-Classical-ML-Architecture.jpg"> |

| 📌 ANALYTICS PLATFORM ARCHITECTURE:- |
| --------- |
| __REALTIME USE CASE__ |
| <img src="/Images/12-Analytics-Platform-Architecture.jpg"> |

| 📌 NATIVE FEATURES OF APIM:- |
| --------- |
| __🚀 "Load Balance" Multiple Backend APIs.__ |
| __🚀 Authentication__ |
| __✅ APIM Service will call the Backend APIs on behalf of Application using Managed Identity.__ |
| __✅ Managed Identity should have the right RBAC to access the Backend APIs.__ |
| __✅ In order to secure how application access APIM, we can apply authentication on the application level. App will be authenticated with APIM Subscription Key to access the correct Backend API configured in APIM using Managed Identity.__ |
| __✅ There can be repeated requests to backend APIs. For such use case, we use "APIM Caching"__ |
| __✅ Tracing - logs and metrics for troubleshooting.__ |
| __✅ Define a Mock API.__ |
| __✅ Fetch Logs and Metrics from Azure Monitor.__
| __🚀 Define Policy and apply for each API. Policies in APIM are XML Definition.__ |
| __🚀 APIM Authentication Features defined in Pt 2, works well with Backend APIs and LLM Models - OpenAI, Mistral.... Multiple requests can be load balanced & send to Multiple instances of LLMS. In such Scenarios, using below features of LBs can be very useful - Priority, Weight, Retry, Circuit Breaker.__ |

| 📌 GEN AI CAPABILITY IN APIM:- |
| --------- |
| __🚀 LLM Token Limit__ |
| __Limitations/Constraints of LLM:__ ✅ No. of Tokens available per model; ✅ No. of Tokens per region |
| __Mitigation:__ ✅ Create LLM instance in different regions and use Priority and Weight to prioritize the LLM instance; ✅ With retry, we detect, if we have hit the limitation of any LLM Instances. if yes, then retry on the next available LLM instances in other region. |
| Now in order to avoid hitting limitation in each LLM instance (Per model and/or Per region), there is "a new GENAI capability available in APIM" - __"LLM Token Limit"__. This is available using APIM Policy. This will allow APIM to limit, No of tokens issued by Application or by user to specific LLM Models. |
| __🚀 LLM Token Limit__ |
| Applying Policy using this feature, we can get specific metrics related to LLMs: |
| __✅ No of Tokens consumed.__ |
| __✅ No of remaining tokens.__ |
| __✅ Tokens available per applications.__ |


