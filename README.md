&lt;!DOCTYPE html&gt;
&lt;html lang="ar"&gt;
&lt;head&gt;
    &lt;meta charset="UTF-8"&gt;
    &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
    &lt;title&gt;ذكاء محمد الاصطناعي&lt;/title&gt;
    &lt;style&gt;
        body { font-family: Arial, sans-serif; text-align: center; }
        textarea { width: 80%; height: 100px; }
        button { padding: 10px; margin-top: 10px; cursor: pointer; }
        .premium { color: gold; font-weight: bold; }
    &lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;
    &lt;h1&gt;🤖 مرحبًا في ذكاء محمد الاصطناعي!&lt;/h1&gt;
    &lt;p&gt;اكتب سؤالك أدناه وسيتم الرد عليك:&lt;/p&gt;
    
    &lt;textarea id="userInput"&gt;&lt;/textarea&gt;&lt;br&gt;
    &lt;button onclick="askAI(false)"&gt;إرسال&lt;/button&gt;
    
    &lt;h2 class="premium"&gt;🚀 اشترك في الباقة المميزة مقابل 5$&lt;/h2&gt;
    &lt;button onclick="subscribe()"&gt;اشترك الآن&lt;/button&gt;
    
    &lt;p id="response"&gt;&lt;/p&gt;

    &lt;script&gt;
        async function askAI(premium) {
            let userInput = document.getElementById("userInput").value;
            let apiKey = "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"; // ضع مفتاح OpenAI API هنا
            let model = premium ? "gpt-4" : "gpt-3.5-turbo"; // تفعيل GPT-4 للمشتركين

            let response = await fetch("https://api.openai.com/v1/chat/completions", {
                method: "POST",
                headers: {
                    "Content-Type": "application/json",
                    "Authorization": `Bearer ${apiKey}`
                },
                body: JSON.stringify({
                    model: model,
                    messages: [{role: "user", content: userInput}]
                })
            });

            let data = await response.json();
            document.getElementById("response").innerText = data.choices[0].message.content;
        }

        function subscribe() {
            window.location.href = "https://buy.stripe.com/test_dR628z0qQ9QofG8144"
        }
    &lt;/script&gt;
&lt;/body&gt;
&lt;/html&gt;
