<script lang="ts">
  import { appName } from '$lib/app-info'

  import vCard from 'vcf'
  var card = new vCard()
  card.set('fn', 'John Doe')
  card.set('org', 'ACME Inc.')
  console.log(card.toString('4.0'))

  var parsedCard = vCard.parse(card.toString('4.0'))
  console.log(parsedCard)
</script>

<div
  class="min-h-[calc(100vh-96px)] flex flex-col items-start justify-center max-w-[700px] m-auto gap-6 pb-5 text-sm"
>
  <h1 class="text-xl">Welcome to the {appName}</h1>

  <div class="max-w-[590px]">
    <div class="mb-4">
      <span class="text-lg mb-4">Name</span>
      <input
        class="input input-bordered focus:outline-none w-full px-3 inline-block"
        type="text"
        name="name"
      />
    </div>
    <!-- html form elements: name, organization, phone number -->
    <div class="mb-4">
      <span class="text-lg mb-4">Organization</span>
      <input
        class="input input-bordered focus:outline-none w-full px-3 inline-block"
        type="text"
        name="organization"
      />
    </div>
    <!-- button to generate vCard -->
    <button class="btn btn-primary">Generate vCard</button>
  </div>
</div>
