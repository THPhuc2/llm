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
# Tùy chọn cho mô hình 8bit hoặc 4bit
LOAD_IN_8BIT="True"  # hoặc "False" nếu không sử dụng
LOAD_IN_4BIT="True"  # Chỉ nên đặt là "True" nếu không có GPU đủ mạnh
```
Note: nếu không chạy bằng 8bit thì nên "False" thì thời gian chạy >= 500s/infer tùy vào từng ảnh or prompt được đặt ra
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

- Note: ảnh đầu vào là ảnh .png
```bash
cd src
python gradio_llm.py
```

## Cấu trúc dự án

- app.py: Tập tin chính để khởi chạy Gradio UI.
- requirements.txt: File chứa danh sách các thư viện cần cài đặt.
- .env: File chứa các biến môi trường để cấu hình mô hình và các tham số khác.
- llmserve/: Thư mục chứa các tệp mã nguồn liên quan đến mô hình và xử lý hình ảnh.

## Các tham số đầu vào trong UI
- Ứng dụng sử dụng Gradio UI với các tham số sau:

- Hình ảnh đầu vào: Người dùng có thể tải lên hình ảnh. (note yêu cầu ảnh .png)
- Câu hỏi: Nhập câu hỏi liên quan đến hình ảnh (ví dụ: "nội dung bức ảnh này bằng tiếng Việt và định dạng json").
- Max Length: Độ dài tối đa của câu trả lời.
- Temperature: Điều chỉnh sự ngẫu nhiên trong kết quả (giá trị từ 0 đến 1).
- Top-p: Giới hạn trên của các từ được chọn trong khi tạo câu trả lời.
- Repetition Penalty: Điều chỉnh hình phạt khi lặp lại từ trong câu trả lời.


### Những điểm đã được sửa đổi:
1. **Yêu cầu hệ thống**: Đã thêm một số lưu ý về cấu hình mô hình 8bit/4bit và yêu cầu bộ nhớ GPU.
2. **Cài đặt**: Thêm hướng dẫn sử dụng script `install.sh` thay vì chỉ cài đặt thủ công qua `requirements.txt` cho người dùng tiện lợi hơn.
3. **Cấu trúc dự án**: Làm rõ hơn về cấu trúc thư mục và các tệp liên quan.
4. **Tham số đầu vào**: Cung cấp thông tin chi tiết hơn về các tham số trong UI, đặc biệt là hình ảnh đầu vào yêu cầu định dạng `.png`.

Với các thay đổi này, README của bạn sẽ dễ hiểu và chi tiết hơn cho người dùng muốn triển khai và sử dụng ứng dụng.


## Liên hệ
- Huggingface: THP2903/Erax_llm_ocr
- Email: PhucTH2903@gmail.com
- Cảm ơn bạn đã sử dụng dự án LLMserve. Nếu bạn có bất kỳ câu hỏi nào, hãy mở một issue trên GitHub hoặc gửi một email cho chúng tôi.


