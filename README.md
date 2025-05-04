<section id="order" class="p-8 bg-pink-50">
  <h3 class="text-xl font-semibold mb-4">نموذج الطلب</h3>
  <form onsubmit="sendToWhatsApp(event)" class="max-w-md mx-auto bg-white p-6 rounded shadow">
    <label class="block mb-2">الاسم الكامل</label>
    <input type="text" class="w-full border p-2 mb-4" id="fullName" required><label class="block mb-2">رقم الهاتف</label>
<input type="tel" class="w-full border p-2 mb-4" id="phoneNumber" required>

<label class="block mb-2">العنوان</label>
<textarea class="w-full border p-2 mb-4" id="address" required></textarea>

<label class="block mb-2">المنتج المطلوب</label>
<input type="text" class="w-full border p-2 mb-4" id="productName" required>

<button type="submit" class="bg-green-600 text-white py-2 px-4 rounded">إرسال الطلب عبر واتساب</button>

  </form>
</section><script>
  function sendToWhatsApp(event) {
    event.preventDefault();
    const name = document.getElementById("fullName").value;
    const phone = document.getElementById("phoneNumber").value;
    const address = document.getElementById("address").value;
    const product = document.getElementById("productName").value;

    const message = `مرحبًا، أود طلب المنتج التالي:\n\nالاسم: ${name}\nرقم الهاتف: ${phone}\nالعنوان: ${address}\nالمنتج المطلوب: ${product}`;

    const encodedMessage = encodeURIComponent(message);
    const whatsappNumber = "212654652593"; // رقم المغرب بدون 0

    window.open(`https://wa.me/${whatsappNumber}?text=${encodedMessage}`, "_blank");
  }
</script>
