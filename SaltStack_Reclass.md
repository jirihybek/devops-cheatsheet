# Salt Cheatsheet

**Retreive pillar data**

```bash
salt-call pillar.data $KEY
```

**Refresh pillar**

```bash
salt '*' saltutil.refresh_pillar
```

**Apply state**

```bash
salt '*' state.apply salt
```