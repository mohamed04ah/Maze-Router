<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
</head>
<body>

  <h1>Maze Router</h1>

  <h2>Overview</h2>
  <p>
    This project implements a <strong>multi-layer grid-based maze router</strong> using a modified version of <strong>Lee's algorithm</strong>. It computes optimal routing paths for multiple nets with support for obstacles, directional and via penalties, and interactive visualization via a GUI.
  </p>
  <p>This notebook-based router supports:</p>
  <ul>
    <li>Multi-layer routing with up to 2 layers</li>
    <li>Multiple nets with multiple pins</li>
    <li>Obstacle avoidance and via switching</li>
    <li>Direction and via cost penalties</li>
    <li>Heuristic-based routing and backtracking</li>
    <li>Interactive GUI visualization using <code>tkinter</code></li>
  </ul>
  <p>The project is written in Python and implemented in a Jupyter Notebook for interactive experimentation and development.</p>

  <hr>

  <h2>Input File Format</h2>
  <p>The router expects an input file (e.g. <code>input1.txt</code>) with the following format:</p>
  <pre>
&lt;rows&gt;, &lt;cols&gt;, &lt;DirectionPenalty&gt;, &lt;ViaPenalty&gt;
OBS (&lt;layer&gt;, &lt;row&gt;, &lt;col&gt;)
net (&lt;layer&gt;, &lt;row&gt;, &lt;col&gt;) (&lt;layer&gt;, &lt;row&gt;, &lt;col&gt;) ...
...
  </pre>

  <h3>Example:</h3>
  <pre>
10,10,3,5
OBS (0,2,2)
OBS (1,4,4)
net (0,0,0) (0,0,5)
net (1,3,3) (0,9,9)
  </pre>
  <blockquote>
    ⚠️ Format: <strong>(layer, row, col)</strong><br>
    Internally accessed as: <code>grid[layer][row][col]</code>
  </blockquote>

  <hr>

  <h2>How to Run</h2>
  <ol>
    <li>Place your input file (e.g. <code>input1.txt</code>) in the working directory.</li>
    <li>Open <code>MazeRouter.ipynb</code> in Jupyter Notebook:
      <pre><code>jupyter notebook MazeRouter.ipynb</code></pre>
    </li>
    <li>Run all notebook cells (Shift + Enter).</li>
    <li>When the GUI launches, enter the filename (e.g. <code>input1.txt</code>).</li>
    <li>The routed paths and net costs will be displayed interactively.</li>
  </ol>

  <hr>

  <h2>Features</h2>
  <ul>
    <li>✅ Modified Lee’s Algorithm (2D and 3D)</li>
    <li>✅ Same-layer and cross-layer routing</li>
    <li>✅ Directional and via penalty control</li>
    <li>✅ Dynamic back-propagation to build final paths</li>
    <li>✅ GUI for layer-wise routing visualization</li>
    <li>✅ Supports multi-pin nets</li>
    <li>✅ Cost display per net</li>
  </ul>

  <hr>

  <h2>Limitations</h2>
  <ul>
    <li>No Dynamic Re-routing: Once a path is blocked by earlier nets, failed nets are skipped entirely.</li>
    <li>No Congestion Awareness Beyond Cost: Routing decisions are cost-based but do not consider grid congestion over time.</li>
    <li>No Parallelism: All nets are routed sequentially, missing out on optimization opportunities via concurrent routing or lookahead.</li>
  </ul>

  <hr>

  <h2>Future Enhancements</h2>
  <ul>
    <li>Net path export to file (CSV or JSON)</li>
    <li>Dynamic in-GUI obstacle/net placement</li>
    <li>Real-time routing animation</li>
    <li>Support for more than 2 layers</li>
    <li>Integration with congestion-aware heuristics</li>
  </ul>

  <hr>

  <h2>Project Details</h2>
  <ul>
    <li><strong>Course:</strong> CSCE3304 – Spring 2025</li>
    <li><strong>Project:</strong> Maze Routing in Jupyter with Lee’s Algorithm</li>
    <li><strong>Status:</strong> ✅ Final Version – Fully Functional</li>
    <li><strong>Notebook File:</strong> <code>MazeRouter.ipynb</code></li>
  </ul>

  <hr>

  <h2>Authors</h2>
  <p><strong>Mohamed Ahmed, Youssef Elmahdy, Hussien Heggi</strong></p>

  <hr>

  <h2>License</h2>
  <p>
    This project is licensed for academic and educational use only.
    Commercial redistribution is not permitted without prior written consent.
  </p>

</body>
</html>
