<script lang="ts">
  import { getModelLogo } from '../../lib/modelLogos';

  interface ModelCardProps {
      entry: {
          collection: string;
          slug: string;
          data: {
              title: string;
              description: string;
              device: string;
          };
      };
  }
  export let entry: ModelCardProps["entry"];
  
  // Get the logo URL for this model
  const logoUrl = getModelLogo(entry.data.title);
</script>

<a
href=https://huggingface.co/{entry.data.title}
class="relative group flex flex-nowrap py-3 px-4 pr-10 rounded-lg border border-black/15 dark:border-white/20 hover:bg-black/5 dark:hover:bg-white/5 hover:text-black dark:hover:text-white transition-colors duration-300 ease-in-out"
>
<div class="flex items-center gap-3">
  <img src={logoUrl} alt="Model logo" class="w-8 h-8 object-contain" />
  <div class="flex flex-col flex-1 truncate">
    <div class="font-semibold">{entry.data.title}</div>
    <div class="text-sm">on {entry.data.device}</div>
  </div>
</div>
<svg
  xmlns="http://www.w3.org/2000/svg"
  viewBox="0 0 24 24"
  class="absolute top-1/2 right-2 -translate-y-1/2 size-5 stroke-2 fill-none stroke-current"
>
  <line
    x1="5"
    y1="12"
    x2="19"
    y2="12"
    class="translate-x-3 group-hover:translate-x-0 scale-x-0 group-hover:scale-x-100 transition-transform duration-300 ease-in-out"
  />
  <polyline
    points="12 5 19 12 12 19"
    class="-translate-x-1 group-hover:translate-x-0 transition-transform duration-300 ease-in-out"
  />
</svg>
</a>