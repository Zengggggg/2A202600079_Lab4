# CASE 1: Direct Answer (Không dùng tool)

**User:**  

```powershell
Xin chào! Tôi đang muốn đi du lịch nhưng chưa biết đi đâu.
```
**Kết quả:**

```powershell
TravelBuddy: Chào bạn! Bạn có một cái đầu đầy ý tưởng, và mình ở đây để giúp bạn. Bạn có thích điểm đến nào trong nước không? Hoặc có thể cho mình biết về sở thích của bạn, như bạn muốn thư giãn, khám phá văn hóa, hay tham gia các hoạt động mạo hiểm nhé?
```
# Test 2 - Single Tool Call

**User:**  

```powershell
Tìm giúp tôi chuyến bay từ Hà Nội đi Đà Nẵng
```

**Kết quả:**
```powershell
TravelBuddy đang suy nghĩ...
Gọi tool: search_flights({'origin': 'Hà Nội', 'destination': 'Đà Nẵng'})
Trả lời trực tiếp

TravelBuddy: Mình đã tìm thấy một số chuyến bay từ Hà Nội đi Đà Nẵng như sau:

1. **VietJet Air**: 08:30 → 09:50 | Hạng phổ thông | 890.000đ
2. **Bamboo Airways**: 11:00 → 12:20 | Hạng phổ thông | 1.200.000đ
3. **Vietnam Airlines**: 06:00 → 07:20 | Hạng phổ thông | 1.450.000đ
4. **Vietnam Airlines**: 14:00 → 15:20 | Hạng thương gia | 2.800.000đ

Bạn có chuyến bay nào bạn thích không? Và cho mình biết ngân sách tổng thể của bạn để mình có thể giúp bạn lên kế hoạch cho phần lưu trú và chi phí khác nhé!
```

# Test 3 - Multi-Step Tool Chaining

**User:**  

```powershell
 Tôi ở Hà Nội, muốn đi Phú Quốc 2 đêm, budget 5 triệu. Tư vấn giúp!
```


**Kết quả:**
```powershell
TravelBuddy đang suy nghĩ...
Gọi tool: search_flights({'origin': 'Hà Nội', 'destination': 'Phú Quốc'})
Gọi tool: calculate_budget({'total_budget': 5000000, 'expenses': 'vé_máy_bay:1350000'})
Gọi tool: search_hotels({'city': 'Phú Quốc', 'max_price_per_night': 1825000})
Trả lời trực tiếp

TravelBuddy: Dưới đây là kế hoạch chuyến đi từ Hà Nội đến Phú Quốc cho 2 đêm:

**Chuyến bay:**
- **VietJet Air**: 10:00 → 12:15 | Hạng phổ thông | Giá: 1.350.000đ

**Khách sạn:**
- **Sol by Meliá**: ⭐ 4 sao | Bãi Trường | Giá: 1.500.000đ/đêm
- Tổng chi phí cho 2 đêm: 3.000.000đ

**Tổng chi phí ước tính:**
- Vé máy bay: 1.350.000đ
- Khách sạn (2 đêm): 3.000.000đ
- **Tổng cộng:** 4.350.000đ

**Ngân sách còn lại:** 650.000đ (dành cho ăn uống và tham quan).

Bạn thấy kế hoạch này có ổn không? Có thêm nhu cầu gì khác không?
```

# Test 4 - Missing Info / Clarification

**User:**  

```powershell
 Tôi muốn đặt khách sạn
```

**Kết quả:**

```powershell
TravelBuddy đang suy nghĩ...
Trả lời trực tiếp

TravelBuddy: Được rồi! Bạn muốn đặt khách sạn tại địa điểm nào? Và bạn có ngân sách cụ thể cho khách sạn mỗi đêm không? Hãy cho mình biết thêm chi tiết để mình có thể tìm khách sạn phù hợp cho bạn nhé!
```
# Test 5 - Guardrail / Refusal

**User:**  

```powershell
 Giải giúp tôi bài tập lập trình Python về linked list
```

**Kết quả:**

```powershell
TravelBuddy đang suy nghĩ...
Trả lời trực tiếp

TravelBuddy: Mình là trợ lý du lịch nên chỉ hỗ trợ các vấn đề liên quan đến chuyến đi, vé máy bay và khách sạn thôi nhé 😊
```



