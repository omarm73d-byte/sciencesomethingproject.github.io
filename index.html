<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Series & Parallel Circuits Lab</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #0b0f19;
            color: #f3f4f6;
            text-align: center;
            margin: 0;
            padding: 20px;
        }
        h1 { color: #38bdf8; margin-bottom: 5px; }
        p.subtitle { color: #9ca3af; margin-top: 0; margin-bottom: 30px; }
        .container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            max-width: 1100px;
            margin: 0 auto;
        }
        .circuit-card {
            background-color: #1e293b;
            border: 1px solid #334155;
            border-radius: 12px;
            padding: 15px;
            width: 320px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.3);
        }
        h3 { color: #38bdf8; margin-top: 0; font-size: 16px; }
        canvas {
            background-color: #0f172a;
            border-radius: 8px;
            border: 1px solid #475569;
            margin-bottom: 10px;
        }
        .meter-display {
            background-color: #090d16;
            border: 1px solid #22c55e;
            color: #22c55e;
            font-family: monospace;
            padding: 8px;
            border-radius: 6px;
            font-size: 13px;
            text-align: left;
            margin-bottom: 10px;
            min-height: 75px;
        }
        .btn {
            background-color: #3b82f6;
            color: white;
            border: none;
            padding: 8px 12px;
            font-size: 13px;
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            width: 100%;
            transition: background 0.2s;
        }
        .btn:hover { background-color: #2563eb; }
    </style>
</head>
<body>

    <h1>⚡ Series & Parallel Circuits Science Lab</h1>
    <p class="subtitle">Explore how adding cells in Series vs. Parallel affects voltage, current, and electron flow!</p>

    <div class="container" id="circuit-container"></div>

    <script>
        // Circuit configurations including Series and Parallel cell setups
        const circuits = [
            { id: 1, name: "Circuit 1: Single Cell Baseline", type: "Standard", cells: 1, cellVoltage: 12, resistance: 4 },
            { id: 2, name: "Circuit 2: Cells in SERIES (+)", type: "Series", cells: 2, cellVoltage: 6, resistance: 4 },
            { id: 3, name: "Circuit 3: Cells in PARALLEL (||)", type: "Parallel", cells: 2, cellVoltage: 12, resistance: 4 },
            { id: 4, name: "Circuit 4: Multi-Cell Series Lab", type: "Series", cells: 3, cellVoltage: 5, resistance: 3 }
        ];

        let circuitStats = {};
        let electrons = {};

        const container = document.getElementById("circuit-container");

        circuits.forEach(circ => {
            circuitStats[circ.id] = { time: 0, charge: 0 };
            
            electrons[circ.id] = [];
            for(let i=0; i<5; i++) {
                electrons[circ.id].push({ pos: i * 50 });
            }

            const card = document.createElement("div");
            card.className = "circuit-card";
            card.innerHTML = `
                <h3>${circ.name}</h3>
                <canvas id="canvas-${circ.id}" width="280" height="100"></canvas>
                <div class="meter-display" id="meter-${circ.id}">Loading...</div>
                <button class="btn" onclick="addCell(${circ.id})">🔋 Add Cell (${circ.type})</button>
            `;
            container.appendChild(card);
        });

        function addCell(id) {
            const circ = circuits.find(c => c.id === id);
            circ.cells += 1;
            if (circ.cells > 4) circ.cells = 1; // Loop back down after 4 cells
        }

        let lastTime = performance.now();

        function updateSimulation(currentTime) {
            const dt = (currentTime - lastTime) / 1000;
            lastTime = currentTime;

            circuits.forEach(circ => {
                const stats = circuitStats[circ.id];
                stats.time += dt;

                // Calculate total voltage based on configuration type
                let totalVoltage = 0;
                if (circ.type === "Parallel") {
                    // Parallel: Voltage stays equal to a single cell regardless of how many cells are added
                    totalVoltage = circ.cellVoltage;
                } else {
                    // Series/Standard: Voltages add up together
                    totalVoltage = circ.cells * circ.cellVoltage;
                }

                // Ohm's Law: I = V / R
                const current = totalVoltage / circ.resistance;
                stats.charge = current * stats.time; // Q = I * t

                // Update Meter Screen Text
                const meterBox = document.getElementById(`meter-${circ.id}`);
                if (circ.type === "Parallel") {
                    meterBox.innerHTML = `[PARALLEL BATTERY PACK]<br>• Active Cells: <b>${circ.cells} in Parallel</b><br>• Voltage (Constant): <b>${totalVoltage.toFixed(1)} V</b><br>• Current (Intensity): ${current.toFixed(2)} A`;
                } else if (circ.type === "Series") {
                    meterBox.innerHTML = `[SERIES BATTERY PACK]<br>• Active Cells: <b>${circ.cells} in Series</b><br>• Total Voltage (Added): <b>${totalVoltage.toFixed(1)} V</b><br>• Current (Intensity): ${current.toFixed(2)} A`;
                } else {
                    meterBox.innerHTML = `[STANDARD CIRCUIT]<br>• Cells: <b>${circ.cells}</b> | Voltage: <b>${totalVoltage.toFixed(1)} V</b><br>• Current: ${current.toFixed(2)} A<br>• Resistance: ${circ.resistance} Ω`;
                }

                // Render Canvas Graphics & Moving Electrons
                const canvas = document.getElementById(`canvas-${circ.id}`);
                const ctx = canvas.getContext("2d");
                ctx.clearRect(0, 0, canvas.width, canvas.height);

                // Draw Circuit Wire Path
                ctx.strokeStyle = "#475569";
                ctx.lineWidth = 3;
                ctx.strokeRect(20, 15, 240, 70);

                // Draw Battery Cells visually based on count and type
                ctx.fillStyle = "#ef4444";
                if (circ.type === "Parallel") {
                    // Draw multiple cells stacked side-by-side (Parallel representation)
                    for (let c = 0; c < circ.cells; c++) {
                        ctx.fillRect(25 + (c * 8), 35, 6, 30);
                    }
                } else {
                    // Draw multiple cells connected end-to-end (Series representation)
                    for (let c = 0; c < circ.cells; c++) {
                        ctx.fillRect(25 + (c * 12), 38, 10, 24);
                    }
                }

                // Draw Resistor
                ctx.fillStyle = "#38bdf8";
                ctx.fillRect(242, 35, 12, 30);

                ctx.fillStyle = "#9ca3af";
                ctx.font = "9px sans-serif";
                ctx.fillText(circ.type.toUpperCase(), 22, 28);
                ctx.fillText("RES", 240, 28);

                // Animate Electrons moving along the path (Perimeter = 620)
                const perimeter = 620;
                const speed = current * 22;

                ctx.fillStyle = "#22c55e";
                electrons[circ.id].forEach(el => {
                    el.pos = (el.pos + speed * dt) % perimeter;
                    
                    let x = 0, y = 0;
                    let p = el.pos;
                    if (p < 240) { x = 20 + p; y = 15; }
                    else if (p < 300) { x = 260; y = 15 + (p - 240); }
                    else if (p < 540) { x = 260 - (p - 300); y = 85; }
                    else { x = 20; y = 85 - (p - 540); }

                    ctx.beginPath();
                    ctx.arc(x, y, 3.5, 0, Math.PI * 2);
                    ctx.fill();
                });
            });

            requestAnimationFrame(updateSimulation);
        }

        requestAnimationFrame(updateSimulation);
    </script>

</body>
</html>
