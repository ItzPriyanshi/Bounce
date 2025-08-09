<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Neon Bounce - README</title>
    <style>
        body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; line-height: 1.6; max-width: 800px; margin: 0 auto; padding: 20px; background: #0f0f23; color: #cccccc; }
        h1 { color: #00e5ff; border-bottom: 2px solid #00e5ff; padding-bottom: 10px; }
        h2 { color: #ff2df0; margin-top: 30px; }
        h3 { color: #66ff99; }
        code { background: #1a1a2e; padding: 2px 6px; border-radius: 4px; color: #00e5ff; }
        pre { background: #1a1a2e; padding: 15px; border-radius: 8px; overflow-x: auto; border-left: 4px solid #00e5ff; }
        ul { padding-left: 20px; }
        li { margin: 8px 0; }
        a { color: #00e5ff; text-decoration: none; }
        a:hover { text-decoration: underline; }
        .highlight { background: rgba(0, 229, 255, 0.1); padding: 10px; border-radius: 6px; border-left: 3px solid #00e5ff; }
    </style>
</head>
<body>
    <h1>Neon Bounce (Bun + Canvas) — Vercel Ready</h1>
    
    <p>A single-page Canvas animation of a bouncing ball inside a spinning neon ring. Optimized for high-DPI displays, uses delta-time physics, and runs entirely client-side. Minimal file setup:</p>
    <ul>
        <li>index.html</li>
        <li>styles.css</li>
        <li>index.js</li>
        <li>package.json</li>
        <li>README.md</li>
    </ul>

    <h2>Features</h2>
    <ul>
        <li>Canvas-based neon ring with glow and rotation</li>
        <li>Realistic ball physics with collisions against a circular boundary</li>
        <li>High-DPI scaling and desynchronized canvas context for smoother rendering</li>
        <li>Pure client-side; no server runtime required</li>
    </ul>

    <h2>Quick Start</h2>
    
    <h3>1) Clone and install (optional if you just open index.html)</h3>
    <div class="highlight">
        <strong>With Bun:</strong>
        <pre><code>bun install</code></pre>
        <strong>With npm (only needed if you change the dev server):</strong>
        <pre><code>npm install</code></pre>
    </div>

    <h3>2) Run locally (dev server)</h3>
    <div class="highlight">
        <strong>Using Bun:</strong>
        <pre><code>bun run dev</code></pre>
        <p>Visit <code>http://localhost:5173</code></p>
    </div>

    <h3>3) Open directly</h3>
    <p>You can open <code>index.html</code> in a browser without any server.</p>

    <h2>Deploy on Vercel</h2>
    <ul>
        <li>This is a static site. You can deploy as-is without a build step.</li>
        <li>If you add an install step, commit <code>bun.lockb</code> (or <code>bun.lock</code>) for reproducible installs.</li>
        <li><strong>Recommended settings:</strong>
            <ul>
                <li>Framework preset: Other</li>
                <li>Build command: (leave empty)</li>
                <li>Output directory: .</li>
                <li>Install command: (none) for pure static, or <code>bun install</code> if you keep dev deps</li>
            </ul>
        </li>
    </ul>

    <h2>Project Structure</h2>
    <ul>
        <li><code>index.html</code>: Minimal document with the canvas and module script</li>
        <li><code>styles.css</code>: Responsive sizing and background</li>
        <li><code>index.js</code>: Animation loop, neon ring rendering, and physics</li>
        <li><code>package.json</code>: Optional local dev server scripts</li>
        <li><code>README.md</code>: This file</li>
    </ul>

    <h2>Controls and Behavior</h2>
    <ul>
        <li>The ring spins continuously; the ball collides with the inner edge of the ring.</li>
        <li>Physics uses delta time, gravity, restitution, friction, and air drag.</li>
        <li>Canvas scales to the viewport while remaining crisp on high-DPI screens.</li>
    </ul>

    <h2>Customization</h2>
    <ul>
        <li><strong>Colors:</strong> Edit CSS variables in <code>styles.css</code> (<code>--neon1</code>, <code>--neon2</code>, <code>--neon3</code>, <code>--bg</code>)</li>
        <li><strong>Spin speed:</strong> Change <code>spin</code> in <code>index.js</code></li>
        <li><strong>Gravity and damping:</strong> Adjust <code>g</code>, <code>rest</code>, <code>fAir</code> in <code>index.js</code></li>
        <li><strong>Ball size:</strong> Derived from canvas size; tweak the multiplier in <code>init()</code></li>
    </ul>

    <h2>Troubleshooting</h2>
    <ul>
        <li><strong>Animation looks blurry:</strong> Ensure devicePixelRatio scaling is active (default). Avoid browser zoom if possible.</li>
        <li><strong>Stutters on some devices:</strong> Close other intensive tabs; the canvas uses requestAnimationFrame. Try smaller canvas size by adjusting <code>#c</code> in <code>styles.css</code>.</li>
        <li><strong>Vercel deploy shows a directory listing:</strong> Ensure <code>index.html</code> is at the project root and no framework build is configured.</li>
    </ul>

    <h2>License</h2>
    <p>MIT (add a LICENSE file if needed)</p>
</body>
</html>
