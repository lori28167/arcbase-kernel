# arcbase-kernel

Repository pacman dei kernel di [Arcbase Desktop](https://github.com/lori28167/arcbase-desktop):

| Pacchetto | Kernel |
|---|---|
| `linux-arcbase` | ultimo **stabile** di kernel.org |
| `linux-lts-arcbase` | ultimo **longterm** (LTS) |

I pacchetti sono compilati con la configurazione di Arcbase
([`config/kernel/arcbase.config`](https://github.com/lori28167/arcbase-desktop/blob/main/config/kernel/arcbase.config))
da [`arcbase-kbuild`](https://github.com/lori28167/arcbase-desktop/tree/main/tools/kernel-mirror). Per ogni versione:

1. verifica la firma GPG dei sorgenti di kernel.org;
2. prova il kernel in QEMU: lo installa con pacman in una VM Arcbase e riavvia;
3. lo pubblica qui (release [`x86_64`](https://github.com/lori28167/arcbase-kernel/releases/tag/x86_64)) solo se la prova passa.

I pacchetti sono firmati con la chiave `D206209C73FFFDEE376A6B01136A0A5B84309D20`
(`arcbase-kernel.asc` tra gli asset).

## Uso

Arcbase Desktop ha già questo repository attivo: i kernel si aggiornano con `sudo arc upgrade`.
Su un sistema in cui non è configurato:

```bash
sudo arcbase-kernel-mirror enable
sudo pacman -S linux-arcbase        # e/o linux-lts-arcbase
```

Non scaricare i pacchetti a mano dalla release: li gestisce pacman.
