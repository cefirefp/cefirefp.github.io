

Esta pàgina recull configuracions internes i procediments tècnics que cal tindre localitzats per al manteniment de les eines del CEFIRE de Formació Professional.

---

## ⚙️ Actualització de la versió de Gesform en el servidor d'actualitzacions

Quan Gesform publique una nova versió, cal descarregar-la i deixar-la disponible en el servidor per a que quan executem els scripts d'actulització descarreguen la versió correcta.

**PROCEDIMENT*

#### 1. Descarregar la nova versió de Gesform

En **Guacamole**, inicia Gesform. Si hi ha una nova versió disponible, l'aplicació ho indicarà i descarregarà el fitxer en aquest directori:

```text
/home/lliurex/APP/.wine/drive_c/users/lliurex/AppData/Local/Temp
```

!!!warning "Important"
    El directori `.wine` està ocult. Si no el veus, activa la visualització de fitxers ocults.

En **Windows**, el fitxer es descarrega en el directori temporal de Windows.

#### 2. Pujar el fitxer al servidor

Puja el fitxer `GesformVersion_xx.zip` al servidor `10.227.228.101`, dins del directori `/opt/lampp/htdocs/gesform/`, amb el comandament següent:

```bash
scp GesformVersion_xx.zip lliurex@10.227.228.101:/opt/lampp/htdocs/gesform/
```

#### 3. Copiar el fitxer en `GESFORMWINDOWS`

Entra en el servidor `10.227.228.101` i situa't en el directori de Gesform:

```bash
ssh lliurex@10.227.228.101
cd /opt/lampp/htdocs/gesform/
```

Després, copia el fitxer descarregat dins del directori `GESFORMWINDOWS` amb el nom `Gesform.zip`:

```bash
cp GesformVersionxx.zip GESFORMWINDOWS/Gesform.zip
```

!!!tip "Comprovació"
    Revisa que el fitxer haja quedat en `/opt/lampp/htdocs/gesform/GESFORMWINDOWS/Gesform.zip` i que el nom respecte les majúscules i minúscules indicades.
