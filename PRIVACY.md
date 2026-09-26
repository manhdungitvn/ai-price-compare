---
layout: default
layout_mode: doc
lang: en
title: Privacy Policy — AI Reviewer & Price Compare
description: Everything stays on your device — no server, no analytics, on-device AI. Privacy policy of the AI Reviewer & Price Compare Chrome extension (EN + VI).
---

# Privacy Policy — AI Reviewer & Price Compare

_Last updated: 26 September 2026_

**Summary: everything stays on your device.** The extension has no server, no account, no analytics and no advertising SDK. AI runs locally in Chrome (Gemini Nano). We never see what you search for or buy.

## What the extension does with data

| Data | Where it comes from | What happens to it | Where it is stored |
|---|---|---|---|
| Product you are viewing (title, price, image URL, page URL) | Read from the current page's structured data (JSON-LD / OpenGraph / heading) by the content script | Shown in the side panel so you can compare it with one click; used to ask supported stores for the same product | `chrome.storage.session` on your device — cleared when Chrome closes |
| Search queries and results | Typed by you, or the detected product | Sent **directly from your browser to the stores' public search pages / APIs** (Tiki, Thế Giới Di Động, Điện Máy Xanh, CellphoneS, FPT Shop, Siêu Thị Chợ Lớn, Lazada, Shopee, TikTok Shop, Amazon, Walmart, Best Buy, eBay) — exactly as if you searched there yourself. Results are cached briefly on your device | `chrome.storage.local` (cache, expires after the TTL you set — default 30 min) |
| Recent searches, saved products, price history | Created by your actions in the side panel; when you open the page of a product you saved, its current price is added to that product's history | Used for the "Recent" list, the ❤️ Saved tab and price-drop alerts | `chrome.storage.local` on your device |
| Discount codes (coupon wallet) | Codes visible on store pages you browse, and codes you type | Stored so they can be tried at that store's checkout **only when you press "Try codes"**; the extension only fills the promo field and presses "Apply" — it never places orders or pays | `chrome.storage.local` on your device |
| Customer reviews on the page you are viewing | Read from the page when you open the "Reviews" tab | Summarised by the on-device AI | Not stored |
| Settings (region, language, enabled stores, affiliate templates…) | Set by you | Applied to the UI | `chrome.storage.sync` (synced between your own Chrome profiles if Chrome Sync is on) |

## What we do **not** do
- We do not run any server and do not transmit your data to us or to third parties.
- We do not use analytics, tracking pixels, fingerprinting or advertising SDKs.
- We do not read pages other than to detect the product / reviews / discount codes described above, and we never modify a store page except for adding our own floating button and cards.
- We do not sell, share or monetise personal data. There is nothing to sell — we do not have it.

## AI processing
Verdicts, review summaries and chat answers are produced by **Gemini Nano, the language model built into Chrome, running on your computer**. No prompt or product data is sent to Google's or anyone's cloud by this extension. If Gemini Nano is not available on your device, the extension falls back to built-in rules — still entirely offline.

## Affiliate links (optional, off by default)
In Settings you can enter your **own** affiliate link templates. When enabled, links that open a store from the side panel or the on-page card carry that affiliate code, and both the side panel footer and the on-page card say so. The price you pay is unchanged. The extension ships with no affiliate codes of its own. It only adds a code to links you click in its own results — never to pages you are browsing — and it never replaces a referral code a link already carries or adds one to links back to the store you are already on.

## Permissions explained
- **Read data on all https sites (content script)** — detects the product on the page you are viewing and shows the floating "Find a better price" button and the "cheaper elsewhere" / coupon cards. Read-only; it only talks to the extension's own background worker.
- **Access to the supported stores (host permissions)** — fetch their public search pages and, for stores that render results with JavaScript, open a background tab that is closed as soon as results are read.
- **storage** — settings, cache, saved items, coupon wallet (all local).
- **sidePanel** — the main user interface.
- **scripting** — run the page-reading script inside store search tabs and in tabs that were already open when the extension was installed.
- **alarms, offscreen, notifications** — periodic price checks of products you saved, and a notification when a price drops.

## Your control
- Clear the cache, disable stores, price tracking, the floating button, the on-page cards or the coupon wallet in **Settings**.
- Remove the extension to delete all local data (Chrome removes extension storage on uninstall).

## Children
The extension is not directed at children under 13 and collects no personal data from anyone.

## Changes
Material changes to this policy will be announced in the extension's release notes and reflected in the date above.

## Contact
Open an issue at https://github.com/manhdungitvn/ai-price-compare/issues or e-mail the address listed on the Chrome Web Store page.

---

# Chính sách quyền riêng tư — AI Reviewer & So sánh giá

_Cập nhật: 26/09/2026_

**Tóm tắt: mọi dữ liệu ở trên máy bạn.** Extension không có máy chủ, không tài khoản, không analytics, không quảng cáo. AI chạy ngay trong Chrome (Gemini Nano). Chúng tôi không bao giờ biết bạn tìm hay mua gì.

## Extension làm gì với dữ liệu
- **Sản phẩm đang xem** (tên, giá, ảnh, URL) được đọc từ dữ liệu có cấu trúc của trang (JSON-LD / OpenGraph / tiêu đề) để hiện trong side panel và tìm ở các sàn khác. Lưu trong `chrome.storage.session`, tự xoá khi đóng Chrome.
- **Từ khoá tìm kiếm & kết quả** được gửi **thẳng từ trình duyệt của bạn tới trang tìm kiếm / API công khai của các sàn** (Tiki, TGDĐ, ĐMX, CellphoneS, FPT Shop, Siêu Thị Chợ Lớn, Lazada, Shopee, TikTok Shop, Amazon, Walmart, Best Buy, eBay) — y như bạn tự tìm trên sàn. Kết quả được cache ngắn hạn trên máy.
- **Tìm gần đây, sản phẩm đã lưu, lịch sử giá, ví mã giảm giá** lưu trong `chrome.storage.local` trên máy bạn. Khi bạn mở trang của một sản phẩm đã lưu, giá hiện tại được thêm vào lịch sử giá của sản phẩm đó. Mã giảm giá chỉ được thử ở trang thanh toán **khi bạn bấm "Thử mã"**; extension chỉ nhập mã và bấm "Áp dụng" — không bao giờ tự đặt hàng hay thanh toán.
- **Review trên trang** chỉ được đọc khi bạn mở tab Review, tóm tắt bằng AI on-device, không lưu.
- **Cài đặt** lưu trong `chrome.storage.sync` (đồng bộ giữa các Chrome của chính bạn nếu bật Chrome Sync).

## Chúng tôi không
- không có máy chủ, không gửi dữ liệu cho chúng tôi hay bên thứ ba;
- không dùng analytics, tracking, quảng cáo;
- không đọc trang ngoài mục đích nhận diện sản phẩm / review / mã giảm giá; không sửa trang sàn ngoài việc thêm nút nổi và thẻ của extension;
- không bán hay chia sẻ dữ liệu cá nhân — vì chúng tôi không hề có.

## AI
Nhận xét, tóm tắt review và trả lời chat do **Gemini Nano tích hợp trong Chrome, chạy trên máy bạn** tạo ra. Extension không gửi prompt hay dữ liệu sản phẩm lên cloud của Google hay bất kỳ ai. Không có Nano thì dùng luật nội bộ — vẫn hoàn toàn offline.

## Link tiếp thị (tuỳ chọn, mặc định tắt)
Bạn có thể tự nhập mẫu link affiliate **của bạn** trong Cài đặt. Khi bật, link mở sàn sẽ mang mã đó, và cả chân trang side panel lẫn thẻ trên trang sản phẩm đều ghi rõ. Giá bạn trả không đổi. Extension không cài sẵn mã affiliate nào. Mã chỉ được gắn vào link bạn bấm trong kết quả của extension — không bao giờ vào trang bạn đang xem — và không bao giờ thay mã giới thiệu mà link đã có, cũng không gắn vào link dẫn về chính sàn bạn đang xem.

## Quyền truy cập
- **Đọc dữ liệu trên mọi trang https** — nhận diện sản phẩm đang xem, hiện nút "Tìm giá tốt hơn" và thẻ "rẻ hơn ở sàn khác" / mã giảm giá. Chỉ đọc; chỉ nói chuyện với worker của chính extension.
- **Truy cập các sàn hỗ trợ** — tải trang tìm kiếm công khai; với sàn render bằng JavaScript, mở tab nền và đóng ngay khi đọc xong.
- **storage** — cài đặt, cache, đã lưu, ví mã (đều local). **sidePanel** — giao diện chính. **scripting** — chạy script đọc trang trong tab tìm kiếm và tab đã mở sẵn. **alarms, offscreen, notifications** — kiểm tra giá định kỳ, báo khi giảm.

## Quyền kiểm soát của bạn
Xoá cache, tắt sàn, tắt theo dõi giá / nút nổi / thẻ trên trang / ví mã trong **Cài đặt**. Gỡ extension là xoá toàn bộ dữ liệu.

## Liên hệ
Mở issue tại https://github.com/manhdungitvn/ai-price-compare/issues hoặc e-mail ghi trên trang Chrome Web Store.
