# Import, export and migration

Rule packs are JSON arrays of executable custom checks. They are not review-data exports or finding reports.

{% hint style="warning" %}
**Power DevBox Pro required to import/export the library and execute custom flags.** [Buy a license](https://power-devbox.lemonsqueezy.com/checkout/buy/729d48f6-cc59-477e-a601-ca99100ffeb3) and activate it in [Settings](../../settings.md).
{% endhint %}

## Export and back up

1. Open **Custom flags** with validated Pro access.
2. Choose **All sections** for a full backup, or a particular section for a scoped pack.
3. Choose **Export JSON** and keep the downloaded `custom-flags.json` somewhere safe.

Section selection determines export scope. Name and status filters help browse the library; they do **not** restrict export to just the visible rows. An All-sections export also includes disabled rules.

## Import a pack

1. Read the pack's JavaScript before importing it.
2. Back up your current library.
3. Select the appropriate section if the pack uses the legacy format without `section` fields.
4. Choose **Import JSON** and select the file.
5. Inspect imported sections, names and enabled status.
6. **Run all flags**, then review findings and execution errors.

Imports are limited to **5 MiB** and must be a JSON array. Entries need a recognised section, a non-empty name and code. A combined-workspace entry looks like:

```json
[
  {
    "section": "solutions",
    "name": "Example policy",
    "live": true,
    "code": "return [];"
  }
]
```

An `id` may appear in exported rules, but import matches existing rules by **section and name**, preserving the existing local ID when it replaces one. A new entry gets a new local ID. Import merges into the library; it does not delete unrelated rules. Importing a rule with the same section/name replaces its saved code and enabled status, so a backup matters.

## Migrating standalone rules

Browser storage from the old standalone domains is not available to this workspace. Export rules from the old tool and import the JSON manually.

Legacy packs can contain entries shaped as `{ name, live, code }`. Choose **AppReview Pro**, **AutoReview Pro** or **CopilotReview Pro** in the library before importing so the missing section can be supplied. If importing from All sections, each rule must carry its own valid `section`.

Rules referencing recognised legacy solution-level keys are moved to **Solutions** on import. Some key names are rewritten—for example, `oData.EnvironmentVariables` becomes `oData.environmentVariables`, and `oData.Solution` becomes the shared object itself.

This is not a complete schema translator. A nested field can still differ, and a rule that mixes app/agent fields with shared solution data may need to be **split into separate rules**. Download current section data, test every migrated rule and inspect execution errors rather than assuming a successful JSON import proves compatibility.

## Moving to another browser

Export rules before changing profile, clearing site data or moving from localhost to the hosted app. The new origin starts with its own library and preferences. Import your backup there, then validate Pro access and rerun the scan against the intended solution.
