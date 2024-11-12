# LLMserve - Gradio UI for Vision-Language Model

LLMserve là một ứng dụng sử dụng mô hình ngôn ngữ hình ảnh (vision-language model) được triển khai thông qua Gradio UI, cho phép người dùng tương tác với mô hình qua hình ảnh và câu hỏi.

## Các tính năng

- **Mô hình Ngôn Ngữ Hình Ảnh (Vision-Language Model)**: Sử dụng mô hình `Qwen2VL` cho phép trả lời câu hỏi liên quan đến nội dung hình ảnh.
- **UI Gradio**: Tích hợp giao diện người dùng đơn giản với Gradio để dễ dàng tương tác với mô hình.
- **Câu hỏi về Hình ảnh**: Người dùng có thể tải lên hình ảnh và đặt câu hỏi về nội dung trong hình ảnh, mô hình sẽ phản hồi dưới dạng văn bản.

## Yêu cầu hệ thống

Để chạy ứng dụng này, bạn cần:

- Python >= 3.9
- GPU (nếu có) với CUDA hỗ trợ cho PyTorch (để chạy mô hình nhanh hơn
- Nếu GPU mạnh có thể chạy 8bit or nếu không vào file .env (NOTE khi chạy 4bit model sẽ dự đoán sai và không chính xác khuyến khích chạy trên GPU > 15GB)
```bash
# LOAD_IN_8BIT="True"
LOAD_IN_4BIT="True" 
```
- Internet (để tải mô hình và các thư viện yêu cầu)

## Cài đặt

### 1. Cài đặt các thư viện cần thiết
Có thể tải và install packet bằng file install.sh

```bash
./install.sh
```
OR

Tạo và kích hoạt môi trường ảo (nếu cần) và cài đặt các thư viện từ `requirements.txt`:

```bash
pip install -r requirements.txt
```

## Run Gradio:

### 1. Run Gradio:

```bash
cd src
python gradio_llm.py
```
