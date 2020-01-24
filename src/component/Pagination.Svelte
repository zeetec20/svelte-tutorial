<script>
    export let previous
    export let next
</script>

<nav aria-label="Page navigation example" style="position: fixed; right: 0; margin-right: 1%;">
    <ul class="pagination">
        <li class="page-item {previous == false ? 'disabled' : ''}"><a class="page-link" href="/tutorial{previous}">Previous</a></li>
        <li class="page-item {next == false ? 'disabled' : ''}"><a class="page-link" href="/tutorial{next}">Next</a></li>
    </ul>
</nav>