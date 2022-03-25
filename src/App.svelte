<script>
	export let name;
	import Form from "./Form.svelte"
</script>
<main>
<!--	<div class="sidebar-wrapper w-1/3">-->
<!--		<div class="tabs-wrapper">-->
<!--			<ul class="flex-col	flex">-->
<!--				<li><a class="flex cursor-pointer submited active"><img class="hidden" src=# alt="arrow">Project Details</a></li>-->
<!--				<li><a class="flex cursor-pointer"><img class="hidden" src=# alt="arrow">Redeemable</a></li>-->
<!--				<li><a class="flex cursor-pointer"><img class="hidden" src=# alt="arrow">Raise Parameters</a></li>-->
<!--				<li><a class="flex cursor-pointer"><img class="hidden" src=# alt="arrow">Seed</a></li>-->
<!--			</ul>-->
<!--		</div>-->
<!--	</div>-->
	<div>
		<h1> FORM </h1>
		<Form />
	</div>
</main>

<style>
	.block {
		cursor: pointer;
	}
	.sidebar-wrapper{
		padding-right: 60px;
	}
	.tabs-wrapper {
		background: #fafbfd;
		padding: 40px 0px 150px;
	}
	.tabs-wrapper ul li a {
		padding: 5px 37px;
		font-size: 20px;
	}
	.tabs-wrapper ul li a:hover,
	.tabs-wrapper ul li a.active {
		background: #fff;
		font-weight: 500;
	}
	.tabs-wrapper ul li a.submited {
		color: #a016a1;
		font-weight: 500;
	}
	.tabs-wrapper ul li a.submited img { display: block !important;}
	.tabs-wrapper ul li a img {
		width: 13px;
		margin-right: 10px;
	}
</style>