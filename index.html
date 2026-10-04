<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>우리은하 3D 구조 시뮬레이션 (중3 과학)</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Three.js CDN -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <!-- OrbitControls CDN -->
    <script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/controls/OrbitControls.js"></script>
    <!-- Tween.js CDN -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/tween.js/18.6.4/tween.umd.js"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Pretendard:wght@300;400;600;700&display=swap');
        
        body {
            font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, system-ui, Roboto, sans-serif;
            margin: 0;
            padding: 0;
            overflow: hidden;
            background-color: #020617;
            color: #f8fafc;
            user-select: none;
        }

        #canvas-container {
            width: 100vw;
            height: 100vh;
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
        }

        .glass-panel {
            background: rgba(15, 23, 42, 0.85);
            backdrop-filter: blur(14px);
            -webkit-backdrop-filter: blur(14px);
            border: 1px solid rgba(255, 255, 255, 0.15);
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.6);
        }

        .custom-scroll::-webkit-scrollbar {
            width: 5px;
        }
        .custom-scroll::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 4px;
        }
        .custom-scroll::-webkit-scrollbar-thumb {
            background: rgba(255, 255, 255, 0.25);
            border-radius: 4px;
        }
    </style>
</head>
<body class="w-full h-screen overflow-hidden">

    <!-- 3D Canvas Container -->
    <div id="canvas-container"></div>

    <!-- Interactive UI Overlay Layer -->
    <div class="relative z-10 pointer-events-none w-full h-full flex flex-col justify-between p-4 md:p-6">
        
        <!-- Top Section: Header & Control Buttons -->
        <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
            
            <!-- Header Panel -->
            <div class="glass-panel rounded-2xl p-4 pointer-events-auto max-w-md w-full">
                <div class="flex items-center gap-3">
                    <div class="p-3 bg-indigo-600/30 border border-indigo-400/40 rounded-xl text-indigo-400">
                        <i class="fa-solid fa-atom text-2xl"></i>
                    </div>
                    <div>
                        <div class="flex items-center gap-2">
                            <h1 class="text-lg font-bold text-white tracking-wide">우리은하 3D 구조</h1>
                            <span class="text-[10px] bg-gradient-to-r from-blue-600 to-indigo-600 text-white px-2 py-0.5 rounded-full font-semibold">중3 과학</span>
                        </div>
                        <p class="text-xs text-indigo-200 mt-0.5">막대나선은하 · 은하면 · 태양계의 위치 탐구</p>
                    </div>
                </div>
            </div>

            <!-- View Angle & Toggle Controls -->
            <div class="glass-panel rounded-2xl p-3 pointer-events-auto flex flex-wrap items-center gap-2 text-sm font-medium">
                <button id="btn-top" onclick="setView('top')" class="px-3.5 py-2 rounded-xl bg-slate-800/90 hover:bg-indigo-600/70 text-slate-200 hover:text-white transition flex items-center gap-2 border border-slate-700 active:scale-95">
                    <i class="fa-solid fa-arrows-up-to-line text-indigo-400"></i> 위에서 보기 (Top)
                </button>
                <button id="btn-side" onclick="setView('side')" class="px-3.5 py-2 rounded-xl bg-slate-800/90 hover:bg-indigo-600/70 text-slate-200 hover:text-white transition flex items-center gap-2 border border-slate-700 active:scale-95">
                    <i class="fa-solid fa-arrows-left-right text-emerald-400"></i> 옆에서 보기 (Side)
                </button>
                <button id="btn-sun" onclick="setView('sun')" class="px-3.5 py-2 rounded-xl bg-slate-800/90 hover:bg-amber-600/70 text-slate-200 hover:text-white transition flex items-center gap-2 border border-slate-700 active:scale-95">
                    <i class="fa-solid fa-sun text-amber-400"></i> 태양계 위치 확대
                </button>
                
                <div class="h-6 w-px bg-slate-700 mx-1 hidden sm:block"></div>

                <!-- Plane Toggle -->
                <button id="btn-plane" onclick="toggleGalacticPlane()" class="px-3 py-2 rounded-xl bg-indigo-600 text-white transition flex items-center gap-1.5 border border-indigo-400 shadow-md">
                    <i class="fa-solid fa-layer-group text-xs"></i> <span id="plane-btn-text" class="text-xs font-semibold">은하면 가이드 : ON</span>
                </button>
                
                <!-- Revolution Toggle -->
                <button id="btn-rotate" onclick="toggleRotation()" class="px-3 py-2 rounded-xl bg-emerald-600 text-white transition flex items-center gap-1.5 border border-emerald-400 shadow-md">
                    <i class="fa-solid fa-rotate text-xs"></i> <span id="rotate-btn-text" class="text-xs font-semibold">공전 : ON</span>
                </button>
            </div>
        </div>

        <!-- Center Bottom: Interaction Guide Tooltip -->
        <div class="self-center glass-panel px-5 py-2 rounded-full text-xs text-slate-200 flex items-center gap-2 pointer-events-auto border border-slate-700/60 shadow-lg mb-2">
            <i class="fa-solid fa-hand-pointer text-indigo-400 animate-pulse"></i>
            <span>마우스 드래그로 <b>3D 회전</b> | 스크롤로 <b>확대/축소</b>할 수 있습니다.</span>
        </div>

        <!-- Bottom Section: Legend and Curriculum Educational Cards -->
        <div class="flex flex-col md:flex-row justify-between items-end gap-4">
            
            <!-- Scale Legend -->
            <div class="glass-panel p-3.5 rounded-2xl pointer-events-auto text-xs text-slate-300 flex flex-col gap-2 border border-slate-700/60 w-full md:w-auto">
                <div class="font-semibold text-slate-100 flex items-center gap-2 border-b border-slate-700/50 pb-1.5">
                    <i class="fa-solid fa-ruler-horizontal text-sky-400"></i> 우리은하 규격 및 위치
                </div>
                <div class="grid grid-cols-2 gap-x-4 gap-y-1.5 text-[11px]">
                    <div class="flex items-center gap-1.5">
                        <span class="w-2.5 h-2.5 rounded-full bg-cyan-400 inline-block"></span>
                        <span>전체 지름: <b class="text-white">약 30,000 pc</b></span>
                    </div>
                    <div class="flex items-center gap-1.5">
                        <span class="w-2.5 h-2.5 rounded-full bg-red-400 inline-block"></span>
                        <span>태양계 거리: <b class="text-white">약 8,500 pc</b></span>
                    </div>
                    <div class="flex items-center gap-1.5">
                        <span class="w-2.5 h-2.5 rounded-full bg-amber-300 inline-block"></span>
                        <span>중심 막대: <b class="text-white">막대나선은하</b></span>
                    </div>
                    <div class="flex items-center gap-1.5">
                        <span class="w-2.5 h-2.5 rounded-full bg-indigo-400 inline-block"></span>
                        <span>태양계 소속: <b class="text-white">오리온자리 팔</b></span>
                    </div>
                </div>
            </div>

            <!-- Learning Concept Card -->
            <div class="glass-panel p-4 rounded-2xl pointer-events-auto max-w-md w-full custom-scroll max-h-[35vh] overflow-y-auto border border-indigo-500/30">
                <div class="flex justify-between items-center mb-2 pb-1.5 border-b border-slate-700/60">
                    <h2 class="font-bold text-slate-100 text-sm flex items-center gap-2">
                        <i class="fa-solid fa-book-open text-indigo-400"></i> 중3 과학교과 핵심 요점
                    </h2>
                    <span class="text-[10px] bg-indigo-500/20 text-indigo-300 px-2 py-0.5 rounded-full border border-indigo-500/30">우리은하</span>
                </div>
                
                <div class="space-y-2 text-xs text-slate-300 leading-relaxed">
                    <div class="p-2 rounded-xl bg-slate-900/60 border border-slate-800">
                        <h3 class="font-bold text-amber-300 text-xs mb-0.5">1. 막대나선은하 (위에서 볼 때)</h3>
                        <p>은하 중심부에 직선 막대 구조가 명확히 보이며, <b>막대의 양쪽 끝에서 여러 쌍의 아름다운 나선팔이 소용돌이치며 연결</b>됩니다.</p>
                    </div>

                    <div class="p-2 rounded-xl bg-slate-900/60 border border-slate-800">
                        <h3 class="font-bold text-cyan-300 text-xs mb-0.5">2. 은하면과 구름 형태의 팽대부 (옆에서 볼 때)</h3>
                        <p>은하면 원반은 얇고 평평하게 별들이 밀집한 반면, 은하 중심의 <b>'팽대부(Bulge)'는 점이 아닌 부드럽고 동그란 구름 형태의 공 모양</b>으로 볼록하게 부풀어 있습니다.</p>
                    </div>

                    <div class="p-2 rounded-xl bg-slate-900/60 border border-slate-800">
                        <h3 class="font-bold text-red-300 text-xs mb-0.5">3. 태양계의 위치 및 공전</h3>
                        <p>태양계는 중심에서 약 <b>8,500 pc</b> 떨어진 오리온자리 나선팔의 <b>은하면 내부</b>에 위치하며 은하 중심을 공전합니다.</p>
                    </div>
                </div>
            </div>

        </div>

    </div>

    <script>
        let scene, camera, renderer, controls;
        let galaxyGroup;
        let planeGroup, sunMarkerGroup;
        let showPlane = true;
        let isRotating = true;

        // Scale: 1 unit = 1,000 pc
        const GALAXY_RADIUS = 15; // 15,000 pc radius
        const SUN_DISTANCE = 8.5; // 8,500 pc from center
        const NUM_PARTICLES = 110000; // Increased particle density for rich photographic feel
        const BAR_LENGTH = 4.3;   // Central bar half-length = 4,300 pc
        const BAR_ANGLE = Math.PI / 6; // 30-degree rotation of central bar

        // Exact coordinates of central bar tips
        const BAR_TIP_X = BAR_LENGTH * Math.cos(BAR_ANGLE);
        const BAR_TIP_Z = BAR_LENGTH * Math.sin(BAR_ANGLE);

        function init() {
            const container = document.getElementById('canvas-container');

            // Scene setup
            scene = new THREE.Scene();
            scene.fog = new THREE.FogExp2(0x020617, 0.012);

            // Camera setup
            camera = new THREE.PerspectiveCamera(45, window.innerWidth / window.innerHeight, 0.1, 1000);
            camera.position.set(0, 28, 0.01);

            // Renderer setup
            renderer = new THREE.WebGLRenderer({ antialias: true, powerPreference: "high-performance" });
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
            renderer.toneMapping = THREE.ACESFilmicToneMapping;
            renderer.toneMappingExposure = 1.25;
            container.appendChild(renderer.domElement);

            // Controls setup
            controls = new THREE.OrbitControls(camera, renderer.domElement);
            controls.enableDamping = true;
            controls.dampingFactor = 0.05;
            controls.maxDistance = 75;
            controls.minDistance = 2;

            // Main rotating galaxy group
            galaxyGroup = new THREE.Group();
            scene.add(galaxyGroup);

            // Light sources
            const ambientLight = new THREE.AmbientLight(0xffffff, 0.6);
            scene.add(ambientLight);

            const centerLight = new THREE.PointLight(0xffedd5, 6, 45);
            centerLight.position.set(0, 0, 0);
            scene.add(centerLight);

            // Create realistic particle texture for glowing stars
            const particleTexture = createGlowStarTexture();

            // Build realistic multi-layer visual components
            createGalaxyParticles(particleTexture);
            createCloudBulge();
            createGalacticPlaneGrid();
            createSunMarker();

            // Window resize event
            window.addEventListener('resize', onWindowResize);

            // Initial view setup
            setView('top');
            
            // Start animation loop
            animate();
        }

        function createGlowStarTexture() {
            const canvas = document.createElement('canvas');
            canvas.width = 64;
            canvas.height = 64;
            const ctx = canvas.getContext('2d');

            const gradient = ctx.createRadialGradient(32, 32, 0, 32, 32, 32);
            gradient.addColorStop(0, 'rgba(255, 255, 255, 1)');
            gradient.addColorStop(0.2, 'rgba(238, 242, 255, 0.95)');
            gradient.addColorStop(0.5, 'rgba(186, 230, 253, 0.45)');
            gradient.addColorStop(0.8, 'rgba(129, 140, 248, 0.1)');
            gradient.addColorStop(1, 'rgba(0, 0, 0, 0)');

            ctx.fillStyle = gradient;
            ctx.fillRect(0, 0, 64, 64);

            return new THREE.CanvasTexture(canvas);
        }

        function createGalaxyParticles(particleTexture) {
            const geometry = new THREE.BufferGeometry();
            const positions = new Float32Array(NUM_PARTICLES * 3);
            const colors = new Float32Array(NUM_PARTICLES * 3);

            // Color palette reflecting real astronomical images
            const colorCore = new THREE.Color('#fffbeb');
            const colorBar = new THREE.Color('#fde047');
            const colorArmInner = new THREE.Color('#38bdf8');
            const colorArmOuter = new THREE.Color('#c084fc');
            const colorDustPink = new THREE.Color('#f472b6');

            const barTipX = BAR_TIP_X;
            const barTipZ = BAR_TIP_Z;

            for (let i = 0; i < NUM_PARTICLES; i++) {
                let x, y, z;
                let color = new THREE.Color();
                const p = Math.random();

                if (p < 0.22) {
                    // 1. Prominent Central Bar Structure
                    const u = (Math.random() - 0.5) * 2; // -1 to 1 along bar length
                    const barPos = u * BAR_LENGTH;

                    // Exponential density dropoff away from center axis
                    const spreadWidth = (Math.random() - 0.5) * 0.85 * Math.exp(-Math.abs(u) * 0.8);
                    const spreadHeight = (Math.random() - 0.5) * 0.08; // Flat disk

                    x = barPos * Math.cos(BAR_ANGLE) - spreadWidth * Math.sin(BAR_ANGLE);
                    z = barPos * Math.sin(BAR_ANGLE) + spreadWidth * Math.cos(BAR_ANGLE);
                    y = spreadHeight;

                    color.copy(colorCore).lerp(colorBar, Math.abs(u));
                }
                else if (p < 0.82) {
                    // 2. Realistic Logarithmic Spiral Arms emerging directly from Bar Tips
                    // 4 arm pairs: 0&1 = Major Arms (Perseus & Scutum-Centaurus), 2&3 = Secondary/Local Arms
                    const armPair = Math.floor(Math.random() * 4);
                    const tipSign = (armPair % 2 === 0) ? 1 : -1;

                    // Bar tip origin point
                    const startX = tipSign * barTipX;
                    const startZ = tipSign * barTipZ;
                    const startAngle = Math.atan2(startZ, startX);

                    // Minor offset for secondary arm branching
                    const armAngleOffset = (armPair >= 2) ? (Math.PI * 0.18 * tipSign) : 0;

                    // Continuous logarithmic distance along arm
                    const distFromTip = Math.pow(Math.random(), 1.15) * (GALAXY_RADIUS - BAR_LENGTH);
                    const currentRadius = BAR_LENGTH + distFromTip;

                    // Natural density wave curvature (Logarithmic spiral)
                    const spiralSpin = startAngle + armAngleOffset + (distFromTip / 2.65);

                    // Organic scatter using Gaussian-like noise (prevents artificial lines)
                    const noiseWidth = (0.25 + distFromTip * 0.09) * Math.pow(Math.random(), 1.2);
                    const noiseAngle = Math.random() * Math.PI * 2;
                    
                    const spreadX = Math.cos(noiseAngle) * noiseWidth;
                    const spreadZ = Math.sin(noiseAngle) * noiseWidth;
                    
                    // Strictly flat Y-plane for disk stars
                    const spreadY = (Math.random() - 0.5) * 0.06;

                    x = currentRadius * Math.cos(spiralSpin) + spreadX;
                    z = currentRadius * Math.sin(spiralSpin) + spreadZ;
                    y = spreadY;

                    const mixRatio = distFromTip / (GALAXY_RADIUS - BAR_LENGTH);
                    if (Math.random() < 0.08) {
                        color.copy(colorDustPink); // Star-forming HII clusters
                    } else {
                        color.copy(colorArmInner).lerp(colorArmOuter, mixRatio);
                    }
                }
                else {
                    // 3. Ambient Inter-arm Fill Stars (removes 'empty void' look, creates realistic photographic depth)
                    const dist = Math.pow(Math.random(), 0.9) * GALAXY_RADIUS;
                    const angle = Math.random() * Math.PI * 2;

                    x = dist * Math.cos(angle);
                    z = dist * Math.sin(angle);
                    y = (Math.random() - 0.5) * 0.08;

                    color.copy(colorArmInner).lerp(colorBar, 0.4).multiplyScalar(0.6);
                }

                positions[i * 3] = x;
                positions[i * 3 + 1] = y;
                positions[i * 3 + 2] = z;

                colors[i * 3] = color.r;
                colors[i * 3 + 1] = color.g;
                colors[i * 3 + 2] = color.b;
            }

            geometry.setAttribute('position', new THREE.BufferAttribute(positions, 3));
            geometry.setAttribute('color', new THREE.BufferAttribute(colors, 3));

            const particleMaterial = new THREE.PointsMaterial({
                size: 0.17,
                vertexColors: true,
                map: particleTexture,
                transparent: true,
                opacity: 0.88,
                blending: THREE.AdditiveBlending,
                depthWrite: false
            });

            const particles = new THREE.Points(geometry, particleMaterial);
            galaxyGroup.add(particles);
        }

        function createCloudBulge() {
            const bulgeGroup = new THREE.Group();

            function createGlowTexture() {
                const canvas = document.createElement('canvas');
                canvas.width = 256;
                canvas.height = 256;
                const ctx = canvas.getContext('2d');

                const gradient = ctx.createRadialGradient(128, 128, 0, 128, 128, 128);
                gradient.addColorStop(0, 'rgba(255, 248, 220, 0.95)');
                gradient.addColorStop(0.2, 'rgba(254, 224, 138, 0.65)');
                gradient.addColorStop(0.55, 'rgba(251, 191, 36, 0.22)');
                gradient.addColorStop(1, 'rgba(251, 191, 36, 0)');

                ctx.fillStyle = gradient;
                ctx.fillRect(0, 0, 256, 256);

                return new THREE.CanvasTexture(canvas);
            }

            const glowTexture = createGlowTexture();

            // Layer 1: Smooth 3D Sphere Mesh with semi-transparent cloud material (< 50% opacity)
            const bulgeGeo = new THREE.SphereGeometry(2.5, 32, 32);
            bulgeGeo.scale(1.15, 0.72, 1.15); // Round elliptical bulge

            const bulgeMat = new THREE.MeshBasicMaterial({
                color: 0xffe8a3,
                transparent: true,
                opacity: 0.36, // Under 50% opacity
                blending: THREE.AdditiveBlending,
                depthWrite: false
            });
            const bulgeMesh = new THREE.Mesh(bulgeGeo, bulgeMat);
            bulgeGroup.add(bulgeMesh);

            // Layer 2: Inner luminous cloud core
            const coreGeo = new THREE.SphereGeometry(1.3, 32, 32);
            coreGeo.scale(1.1, 0.68, 1.1);
            const coreMat = new THREE.MeshBasicMaterial({
                color: 0xffffff,
                transparent: true,
                opacity: 0.42,
                blending: THREE.AdditiveBlending,
                depthWrite: false
            });
            bulgeGroup.add(new THREE.Mesh(coreGeo, coreMat));

            // Layer 3: Soft Volumetric Cloud Sprite Ball
            const spriteMat = new THREE.SpriteMaterial({
                map: glowTexture,
                transparent: true,
                opacity: 0.40,
                blending: THREE.AdditiveBlending,
                depthWrite: false
            });
            const cloudSprite = new THREE.Sprite(spriteMat);
            cloudSprite.scale.set(6.6, 4.5, 1.0);
            bulgeGroup.add(cloudSprite);

            galaxyGroup.add(bulgeGroup);
        }

        function createGalacticPlaneGrid() {
            planeGroup = new THREE.Group();

            // Semi-transparent plane disc
            const discGeo = new THREE.RingGeometry(0.1, GALAXY_RADIUS, 64);
            const discMat = new THREE.MeshBasicMaterial({
                color: 0x0284c7,
                side: THREE.DoubleSide,
                transparent: true,
                opacity: 0.18,
                blending: THREE.AdditiveBlending
            });
            const discMesh = new THREE.Mesh(discGeo, discMat);
            discMesh.rotation.x = Math.PI / 2;
            planeGroup.add(discMesh);

            // Distance ring markers
            const ringDistances = [5, SUN_DISTANCE, GALAXY_RADIUS];
            ringDistances.forEach((r) => {
                const ringGeo = new THREE.BufferGeometry();
                const points = [];
                for (let i = 0; i <= 128; i++) {
                    const theta = (i / 128) * Math.PI * 2;
                    points.push(new THREE.Vector3(r * Math.cos(theta), 0, r * Math.sin(theta)));
                }
                ringGeo.setFromPoints(points);

                const isSunRing = (r === SUN_DISTANCE);
                const ringMat = new THREE.LineBasicMaterial({
                    color: isSunRing ? 0xf87171 : 0x38bdf8,
                    transparent: true,
                    opacity: isSunRing ? 0.85 : 0.45
                });
                planeGroup.add(new THREE.Line(ringGeo, ringMat));
            });

            // "은하면" 3D Text Label
            const planeCanvas = document.createElement('canvas');
            planeCanvas.width = 512;
            planeCanvas.height = 128;
            const ctx = planeCanvas.getContext('2d');
            ctx.fillStyle = '#38bdf8';
            ctx.font = 'Bold 40px Pretendard, sans-serif';
            ctx.textAlign = 'center';
            ctx.fillText('── 은하면 (Galactic Plane) ──', 256, 70);

            const texture = new THREE.CanvasTexture(planeCanvas);
            const spriteMat = new THREE.SpriteMaterial({ map: texture, transparent: true, opacity: 0.9 });
            const sprite = new THREE.Sprite(spriteMat);
            sprite.scale.set(12, 3, 1);
            sprite.position.set(0, 0.25, 14.5);
            planeGroup.add(sprite);

            scene.add(planeGroup);
        }

        function createSunMarker() {
            sunMarkerGroup = new THREE.Group();

            // Solar position calculated on spiral arm at 8.5 kpc
            const startX = BAR_TIP_X;
            const startZ = BAR_TIP_Z;
            const startAngle = Math.atan2(startZ, startX);
            const distFromTip = SUN_DISTANCE - BAR_LENGTH;
            const spiralSpin = startAngle + (distFromTip / 2.65);

            const sunX = SUN_DISTANCE * Math.cos(spiralSpin);
            const sunZ = SUN_DISTANCE * Math.sin(spiralSpin);

            sunMarkerGroup.position.set(sunX, 0, sunZ);

            // Sun sphere
            const sunGeo = new THREE.SphereGeometry(0.32, 16, 16);
            const sunMat = new THREE.MeshBasicMaterial({ color: 0xef4444 });
            sunMarkerGroup.add(new THREE.Mesh(sunGeo, sunMat));

            // Yellow pulsing ring
            const ringGeo = new THREE.RingGeometry(0.45, 0.65, 32);
            const ringMat = new THREE.MeshBasicMaterial({ color: 0xfbbf24, side: THREE.DoubleSide, transparent: true, opacity: 0.9 });
            const ringMesh = new THREE.Mesh(ringGeo, ringMat);
            ringMesh.rotation.x = Math.PI / 2;
            sunMarkerGroup.add(ringMesh);

            // Vertical position dashed line
            const lineGeo = new THREE.BufferGeometry().setFromPoints([
                new THREE.Vector3(0, -1.8, 0),
                new THREE.Vector3(0, 2.2, 0)
            ]);
            const lineMat = new THREE.LineDashedMaterial({ color: 0xef4444, dashSize: 0.2, gapSize: 0.1 });
            const line = new THREE.Line(lineGeo, lineMat);
            line.computeLineDistances();
            sunMarkerGroup.add(line);

            // Text Label
            const canvas = document.createElement('canvas');
            canvas.width = 512;
            canvas.height = 140;
            const ctx = canvas.getContext('2d');
            ctx.fillStyle = '#f87171';
            ctx.font = 'Bold 36px Pretendard, sans-serif';
            ctx.textAlign = 'center';
            ctx.fillText('★ 태양계 (Solar System)', 256, 48);
            ctx.fillStyle = '#fcd34d';
            ctx.font = '26px Pretendard, sans-serif';
            ctx.fillText('중심에서 약 8,500 pc (오리온자리 팔)', 256, 92);

            const texture = new THREE.CanvasTexture(canvas);
            const spriteMat = new THREE.SpriteMaterial({ map: texture, transparent: true });
            const sprite = new THREE.Sprite(spriteMat);
            sprite.scale.set(6.5, 1.8, 1);
            sprite.position.set(0, 3.2, 0);
            sunMarkerGroup.add(sprite);

            // Synchronized rotation inside galaxyGroup
            galaxyGroup.add(sunMarkerGroup);
        }

        function setView(viewType) {
            const duration = 1400;
            let targetPos, targetLookAt;

            if (viewType === 'top') {
                targetPos = new THREE.Vector3(0, 28, 0.01);
                targetLookAt = new THREE.Vector3(0, 0, 0);
            } else if (viewType === 'side') {
                targetPos = new THREE.Vector3(0, 0.1, 28);
                targetLookAt = new THREE.Vector3(0, 0, 0);
            } else if (viewType === 'sun') {
                const worldSunPos = new THREE.Vector3();
                sunMarkerGroup.getWorldPosition(worldSunPos);

                targetPos = new THREE.Vector3(worldSunPos.x + 2.5, worldSunPos.y + 2.8, worldSunPos.z + 3.8);
                targetLookAt = worldSunPos.clone();
            }

            animateCamera(targetPos, targetLookAt, duration);
        }

        function animateCamera(targetPosition, targetLookAt, duration) {
            new TWEEN.Tween(camera.position)
                .to(targetPosition, duration)
                .easing(TWEEN.Easing.Cubic.Out)
                .start();

            new TWEEN.Tween(controls.target)
                .to(targetLookAt, duration)
                .easing(TWEEN.Easing.Cubic.Out)
                .start();
        }

        function toggleGalacticPlane() {
            showPlane = !showPlane;
            planeGroup.visible = showPlane;

            const btnText = document.getElementById('plane-btn-text');
            const btn = document.getElementById('btn-plane');

            if (showPlane) {
                btnText.innerText = "은하면 가이드 : ON";
                btn.className = "px-3 py-2 rounded-xl bg-indigo-600 text-white transition flex items-center gap-1.5 border border-indigo-400 shadow-md";
            } else {
                btnText.innerText = "은하면 가이드 : OFF";
                btn.className = "px-3 py-2 rounded-xl bg-slate-800/90 text-slate-300 hover:text-white transition flex items-center gap-1.5 border border-slate-700";
            }
        }

        function toggleRotation() {
            isRotating = !isRotating;
            const btnText = document.getElementById('rotate-btn-text');
            const btn = document.getElementById('btn-rotate');

            if (isRotating) {
                btnText.innerText = "공전 : ON";
                btn.className = "px-3 py-2 rounded-xl bg-emerald-600 text-white transition flex items-center gap-1.5 border border-emerald-400 shadow-md";
            } else {
                btnText.innerText = "공전 : OFF";
                btn.className = "px-3 py-2 rounded-xl bg-slate-800/90 text-slate-300 hover:text-white transition flex items-center gap-1.5 border border-slate-700";
            }
        }

        function onWindowResize() {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        }

        function animate() {
            requestAnimationFrame(animate);
            TWEEN.update();

            // Galactic orbital revolution (은하 공전)
            if (isRotating && galaxyGroup) {
                galaxyGroup.rotation.y += 0.0006;
            }

            // Pulsing ring effect for Solar System marker
            if (sunMarkerGroup && sunMarkerGroup.children[1]) {
                const time = Date.now() * 0.003;
                const scale = 1 + Math.sin(time) * 0.15;
                sunMarkerGroup.children[1].scale.set(scale, scale, 1);
            }

            controls.update();
            renderer.render(scene, camera);
        }

        window.onload = init;
    </script>
</body>
</html>
