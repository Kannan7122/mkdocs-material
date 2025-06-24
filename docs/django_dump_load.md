# Django Data Backup and Restoration Guide

This guide helps you back up and restore your Django project data using the `dumpdata` and `loaddata` management commands.

## 📁 Navigate to Project Root

Ensure you're in the root directory of your Django project (where `manage.py` is located).

---

## 🔄 Dump Data

1. Configure the desired **database** in your `settings.py` file.
2. Run the following command to export all data into a JSON file:

   ```bash
   python manage.py dumpdata > data.json
   ```

   This will create a `data.json` file containing a backup of your current database records.

---

## ⚙️ Apply Migrations Before Loading Data

Before restoring data into a new or reset database:

1. Ensure your models are migrated:

   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

   This will create the database schema and empty tables.

---

## ❌ Remove Default ContentTypes

When Django applies migrations, it automatically adds default `ContentType` entries. These must be removed before importing data, to avoid conflicts during `loaddata`.

### Run the following commands in the Django shell:

```bash
python manage.py shell
```

```python
from django.contrib.contenttypes.models import ContentType
ContentType.objects.all().delete()
exit()
```

> ⚠️ **Important:** Skipping this step may cause errors related to duplicate `ContentType` entries during data loading.

---

## 📥 Load Data

Now, import the data using:

```bash
python manage.py loaddata data.json
```

This will populate your configured database with the data from `data.json`.

> ❗ **Note:** If any errors occur, ensure that the JSON format is compatible with the current database and models.

---

## ✅ Summary

| Step | Description |
|------|-------------|
| `dumpdata` | Export data to JSON |
| `makemigrations`, `migrate` | Set up database schema |
| Delete `ContentType` | Remove auto-created entries |
| `loaddata` | Restore data from JSON |

---

**Tip:** Always use version control (e.g., Git) and keep a backup of your original `data.json` before performing major data or schema operations.