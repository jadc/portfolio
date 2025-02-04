<script lang="ts">
    let canvas: HTMLCanvasElement;
    let ctx: CanvasRenderingContext2D | null;

    let snowflakes: Array<{x: number, y: number, radius: number, speed: number, wind: number}> = [];
    let frame: number;

    function createSnowflake(width: number, height: number) {
        return {
            x: Math.random() * width,
            y: Math.random() * height,
            radius: Math.random() * 2 + 1,
            speed: Math.random() + 1,
            wind: Math.random() - 0.5
        };
    }

    function animate() {
        if (!ctx) return;

        // Clear last frame
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        snowflakes.forEach(flake => {
            if (!ctx) return;

            // Draw white circle (the snowflake)
            ctx.beginPath();
            ctx.arc(flake.x, flake.y, flake.radius, 0, Math.PI * 2);
            ctx.fillStyle = "white";
            ctx.fill();

            // Update position
            flake.y += flake.speed;
            flake.x += flake.wind;

            // Reset any snowflake that is off screen
            if (flake.y > canvas.height) Object.assign(flake, createSnowflake(canvas.width, -10));
        });

        frame = requestAnimationFrame(animate);
    }

    // Set canvas size to window size
    function updateCanvasDimensions() {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
    }

    $effect(() => {
        // Get canvas context
        if (!canvas) return;
        ctx = canvas.getContext("2d");
        if (!ctx) return;

        // Keep canvas size same as window
        updateCanvasDimensions();
        const observer = new ResizeObserver(updateCanvasDimensions);
        observer.observe(canvas);

        // Create array of snowflakes
        snowflakes = Array(100).fill(null).map(() => createSnowflake(canvas.width, canvas.height));

        // Start animation
        animate();

        return () => {
            if (frame) cancelAnimationFrame(frame);
        };
    });
</script>

<canvas bind:this={canvas} class="fixed flex top-0 left-0 w-screen h-screen bg-gradient-to-t from-night to-sky"></canvas>
