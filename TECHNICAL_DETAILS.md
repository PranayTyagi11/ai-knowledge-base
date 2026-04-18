# Technical Details

## System Architecture

### Frontend Components
- **React Application**: Modern functional components with hooks
- **Chat Interface**: Real-time messaging with loading states
- **Document Management**: File upload and list management
- **Responsive Design**: Tailwind CSS for all screen sizes

### Backend Services
- **Express Server**: RESTful API with middleware
- **Authentication**: JWT token validation
- **File Processing**: PDF text extraction and chunking
- **Vector Operations**: Embedding generation and similarity search

### AI Integration
- **Text Embeddings**: Cohere embed-english-light-v3.0 model
- **Chat Generation**: Cohere command-a-03-2025 model
- **Semantic Search**: Cosine similarity with vector embeddings

## Database Schema

### Documents Table
- `id`: UUID primary key
- `user_id`: UUID for user isolation
- `title`: Document title
- `content`: Text content chunk
- `s3_key`: AWS S3 file reference
- `file_url`: Secure access URL
- `embedding`: Vector embedding (1024 dimensions)
- `chunk_index`: Position in document
- `total_chunks`: Document chunk count
- `created_at`: Timestamp

### Vector Search Function
Custom PostgreSQL function for similarity matching using pgvector extension.

## API Endpoints

### Document Operations
- `POST /upload-and-embed`: Process and store PDF documents
- `GET /test-supabase`: Retrieve document list
- `DELETE /delete-document`: Remove documents and files

### AI Operations
- `POST /query`: Natural language query processing
- `POST /test-cohere-chat`: AI service verification

### File Operations
- `GET /get-signed-url`: Generate secure file access URLs
