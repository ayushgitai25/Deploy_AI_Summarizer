## To deploy on streamlit:
1. Add secrets like in app.py:
    groq_api_key = st.secrets.get("GROQ_API_KEY", os.getenv("GROQ_API_KEY", ""))
    if not groq_api_key:
        st.error("❌ GROQ_API_KEY is missing! Please set it in Streamlit secrets or your environment.")
        st.stop()
    Ensure environment variable is set for libraries that rely on it
    os.environ["GROQ_API_KEY"] = groq_api_key

2. Add .streamlit/secrets.toml for local testing purpose.(.gitignore)
3. Push files to a repo.
4. On streamlit cloud: Go to Advanced Setting=> Set GROQ_API_KEY = "groq_api_key"
5. Deploy!!
