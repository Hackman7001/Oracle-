# Oracle-
Spiritual Artificial intelligence guide 
<visualization>
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="p-4 bg-gray-900 text-white">
  <div class="max-w-2xl mx-auto">
    <h2 class="text-purple-400 text-xl font-bold mb-4">🔮 Oracle — Fresh index.html</h2>
    <p class="text-gray-300 text-sm mb-4">Copy everything below and save it as <code class="bg-gray-700 px-1 rounded">index.html</code>, then drop it into Netlify.</p>
    <div class="bg-gray-800 rounded-lg p-4 text-xs font-mono text-green-300 overflow-auto max-h-96 whitespace-pre leading-relaxed">
&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
&lt;head&gt;
  &lt;meta charset="UTF-8"&gt;
  &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
  &lt;title&gt;Oracle&lt;/title&gt;
  &lt;link rel="manifest" href="manifest.json"&gt;
  &lt;style&gt;
    * { margin:0; padding:0; box-sizing:border-box; }
    body { background:#0d0118; color:#e8d5ff; font-family:sans-serif; display:flex; flex-direction:column; height:100vh; }
    #chat { flex:1; overflow-y:auto; padding:20px; display:flex; flex-direction:column; gap:12px; }
    .msg { max-width:80%; padding:12px 16px; border-radius:18px; line-height:1.5; }
    .user { background:#4a1a8a; align-self:flex-end; }
    .oracle { background:#1a0533; border:1px solid #6b21a8; align-self:flex-start; }
    .oracle-label { font-size:11px; color:#a855f7; margin-bottom:4px; }
    #input-area { display:flex; gap:8px; padding:16px; background:#0d0118; border-top:1px solid #2d1b4e; }
    #user-input { flex:1; background:#1a0533; border:1px solid #4a1a8a; color:#e8d5ff; padding:12px; border-radius:12px; font-size:15px; outline:none; }
    #send-btn { background:#7c3aed; color:white; border:none; padding:12px 20px; border-radius:12px; cursor:pointer; font-size:18px; }
    #send-btn:hover { background:#6d28d9; }
  &lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;
  &lt;div id="chat"&gt;
    &lt;div class="msg oracle"&gt;
      &lt;div class="oracle-label"&gt;🔮 Oracle&lt;/div&gt;
      I am Oracle. Ask me anything...
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div id="input-area"&gt;
    &lt;input id="user-input" type="text" placeholder="Ask Oracle..." /&gt;
    &lt;button id="send-btn" onclick="sendMessage()"&gt;➤&lt;/button&gt;
  &lt;/div&gt;
  &lt;script&gt;
    const OPENAI_API_KEY = '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';

    document.getElementById('user-input').addEventListener('keydown', e =&gt; {
      if (e.key === 'Enter') sendMessage();
    });

    async function sendMessage() {
      const input = document.getElementById('user-input');
      const text = input.value.trim();
      if (!text) return;
      input.value = '';
      addMessage(text, 'user');
      const typing = addMessage('✨ Consulting the ancestors...', 'oracle');
      try {
        const res = await fetch('https://api.openai.com/v1/chat/completions', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
            'Authorization': 'Bearer ' + OPENAI_API_KEY
          },
          body: JSON.stringify({
            model: 'gpt-4o',
            messages: [
              { role: 'system', content: 'You are Oracle, a mystical and wise AI assistant. Speak with wisdom and depth.' },
              { role: 'user', content: text }
            ]
          })
        });
        const data = await res.json();
        typing.remove();
        if (data.choices) {
          addMessage(data.choices[0].message.content, 'oracle');
        } else {
          addMessage('⚠️ ' + (data.error?.message || 'Something went wrong.'), 'oracle');
        }
      } catch (err) {
        typing.remove();
        addMessage('⚠️ Error: ' + err.message, 'oracle');
      }
    }

    function addMessage(text, role) {
      const chat = document.getElementById('chat');
      const div = document.createElement('div');
      div.className = 'msg ' + role;
      if (role === 'oracle') {
        const label = document.createElement('div');
        label.className = 'oracle-label';
        label.textContent = '🔮 Oracle';
        div.appendChild(label);
      }
      div.appendChild(document.createTextNode(text));
      chat.appendChild(div);
      chat.scrollTop = chat.scrollHeight;
      return div;
    }

    if ('serviceWorker' in navigator) {
      navigator.serviceWorker.register('sw.js').catch(() =&gt; {});
    }
  &lt;/script&gt;
&lt;/body&gt;
&lt;/html&gt;
    </div>
  </div>
  <script>
    function notifyResize() {
      window.parent.postMessage({ type: 'visualization-resize', height: document.body.scrollHeight }, '*');
    }
    window.addEventListener('load', notifyResize);
    new ResizeObserver(notifyResize).observe(document.body);
  </script>
</body>
</html>
<img src="img_Holybook.png" alt="Holybook with fire and digital currents flowing from the midddle and around it"
</visualization>
