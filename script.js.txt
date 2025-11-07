// LOGIN REDIRECT
document.addEventListener("DOMContentLoaded", () => {
  const form = document.getElementById("loginForm");
  if (form) {
    form.addEventListener("submit", (e) => {
      e.preventDefault();
      localStorage.setItem("user", document.getElementById("username").value);
      window.location.href = "menu.html";
    });
  }
});

let total = 0;
function addToBill(item, price) {
  const list = document.getElementById("billItems");
  const entry = document.createElement("li");
  entry.textContent = `${item} - ₹${price}`;
  list.appendChild(entry);
  total += price;
  document.getElementById("total").textContent = `Total: ₹${total}`;
  localStorage.setItem("total", total);
}

// SIMULATED PAYMENT
function simulatePayment(method) {
  const loader = document.getElementById("loadingAnim");
  loader.classList.remove("hidden");
  setTimeout(() => {
    loader.classList.add("hidden");
    window.location.href = "success.html";
  }, 3000); // 3-second animation
}
