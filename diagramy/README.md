# Diagramy

Diagramy w dwóch formatach:

1. Mermaid — pliki `.mmd`, renderowane bezpośrednio w GitHub.
2. draw.io — pliki `.drawio` do edycji w https://app.diagrams.net.

## Otwieranie w draw.io

Wariant A — import pliku `.drawio`:

1. https://app.diagrams.net
2. File → Open From → Device, wybór pliku `*.drawio`.

Wariant B — import kodu Mermaid:

1. Arrange → Insert → Advanced → Mermaid.
2. Wklejenie kodu z pliku `.mmd`.
3. Insert.

## Pliki w katalogu

| Plik | Diagram |
|---|---|
| `01-diagram-przypadkow-uzycia.mmd` | Przypadki użycia (Mermaid) |
| `02-diagram-klas.mmd` | Diagram klas (Mermaid) |
| `03-proces-wypozyczenia.mmd` | Proces wypożyczenia / BPMN (Mermaid) |
| `04-diagram-stanow.mmd` | Stany egzemplarza sprzętu (Mermaid) |
| `przypadki-uzycia.drawio` | Przypadki użycia — gotowy plik draw.io (XML) |
| `diagram-klas.drawio` | Diagram klas — gotowy plik draw.io (XML) |

## Skrypt draw.io — diagram przypadków użycia

Zawartość pliku `przypadki-uzycia.drawio`. Alternatywnie: draw.io → Extras → Edit Diagram, wklejenie poniższego XML.

```xml
<mxGraphModel dx="800" dy="600" grid="1" gridSize="10" guides="1" tooltips="1"
  connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0">
  <root>
    <mxCell id="0" />
    <mxCell id="1" parent="0" />
    <!-- Aktorzy -->
    <mxCell id="a1" value="Student" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;" vertex="1" parent="1">
      <mxGeometry x="40" y="120" width="40" height="80" as="geometry" />
    </mxCell>
    <mxCell id="a2" value="Pracownik" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;" vertex="1" parent="1">
      <mxGeometry x="40" y="320" width="40" height="80" as="geometry" />
    </mxCell>
    <mxCell id="a3" value="Administrator" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;" vertex="1" parent="1">
      <mxGeometry x="40" y="520" width="40" height="80" as="geometry" />
    </mxCell>
    <mxCell id="a4" value="Kierownik" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;" vertex="1" parent="1">
      <mxGeometry x="40" y="680" width="40" height="80" as="geometry" />
    </mxCell>
    <!-- Granica systemu -->
    <mxCell id="sys" value="System zarządzania wypożyczalnią" style="rounded=0;whiteSpace=wrap;html=1;verticalAlign=top;fillColor=none;" vertex="1" parent="1">
      <mxGeometry x="300" y="60" width="450" height="760" as="geometry" />
    </mxCell>
    <!-- Przypadki użycia -->
    <mxCell id="u1" value="Zaloguj się" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="360" y="100" width="140" height="50" as="geometry"/></mxCell>
    <mxCell id="u2" value="Przeglądaj katalog" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="360" y="170" width="140" height="50" as="geometry"/></mxCell>
    <mxCell id="u3" value="Zarezerwuj sprzęt" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="360" y="240" width="140" height="50" as="geometry"/></mxCell>
    <mxCell id="u4" value="Anuluj rezerwację" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="360" y="310" width="140" height="50" as="geometry"/></mxCell>
    <mxCell id="u5" value="Wydaj sprzęt" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="560" y="310" width="140" height="50" as="geometry"/></mxCell>
    <mxCell id="u6" value="Przyjmij zwrot" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="560" y="380" width="140" height="50" as="geometry"/></mxCell>
    <mxCell id="u7" value="Zgłoś uszkodzenie" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="560" y="450" width="140" height="50" as="geometry"/></mxCell>
    <mxCell id="u8" value="Zarządzaj katalogiem" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="360" y="520" width="140" height="50" as="geometry"/></mxCell>
    <mxCell id="u9" value="Zarządzaj kontami" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="360" y="590" width="140" height="50" as="geometry"/></mxCell>
    <mxCell id="u10" value="Generuj raporty" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="360" y="680" width="140" height="50" as="geometry"/></mxCell>
    <!-- Powiązania aktor-przypadek -->
    <mxCell id="e1" style="endArrow=none;html=1;" edge="1" parent="1" source="a1" target="u1"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="e2" style="endArrow=none;html=1;" edge="1" parent="1" source="a1" target="u2"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="e3" style="endArrow=none;html=1;" edge="1" parent="1" source="a1" target="u3"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="e4" style="endArrow=none;html=1;" edge="1" parent="1" source="a1" target="u4"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="e5" style="endArrow=none;html=1;" edge="1" parent="1" source="a2" target="u5"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="e6" style="endArrow=none;html=1;" edge="1" parent="1" source="a2" target="u6"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="e7" style="endArrow=none;html=1;" edge="1" parent="1" source="a2" target="u7"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="e8" style="endArrow=none;html=1;" edge="1" parent="1" source="a3" target="u8"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="e9" style="endArrow=none;html=1;" edge="1" parent="1" source="a3" target="u9"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="e10" style="endArrow=none;html=1;" edge="1" parent="1" source="a4" target="u10"><mxGeometry relative="1" as="geometry"/></mxCell>
    <!-- include -->
    <mxCell id="i1" value="&laquo;include&raquo;" style="endArrow=open;dashed=1;html=1;" edge="1" parent="1" source="u3" target="u1"><mxGeometry relative="1" as="geometry"/></mxCell>
  </root>
</mxGraphModel>
```

## Skrypt draw.io — diagram klas

Zawartość pliku `diagram-klas.drawio`. Alternatywnie: Extras → Edit Diagram.

```xml
<mxGraphModel dx="800" dy="600" grid="1" gridSize="10" guides="1" page="1" pageWidth="850" pageHeight="1100">
  <root>
    <mxCell id="0"/>
    <mxCell id="1" parent="0"/>
    <mxCell id="c1" value="Uzytkownik" style="swimlane;html=1;childLayout=stackLayout;startSize=26;horizontal=1;" vertex="1" parent="1">
      <mxGeometry x="40" y="40" width="180" height="120" as="geometry"/>
    </mxCell>
    <mxCell id="c1a" value="+id: int&#10;+imieNazwisko: string&#10;+email: string&#10;+rola: Rola&#10;+aktywny: bool" style="text;html=1;align=left;verticalAlign=top;spacingLeft=4;" vertex="1" parent="c1">
      <mxGeometry y="26" width="180" height="94" as="geometry"/>
    </mxCell>
    <mxCell id="c2" value="Sprzet" style="swimlane;html=1;startSize=26;" vertex="1" parent="1">
      <mxGeometry x="320" y="40" width="190" height="130" as="geometry"/>
    </mxCell>
    <mxCell id="c2a" value="+id: int&#10;+nazwa: string&#10;+nrInwentarzowy: string&#10;+kodQR: string&#10;+stan: StanSprzetu" style="text;html=1;align=left;verticalAlign=top;spacingLeft=4;" vertex="1" parent="c2">
      <mxGeometry y="26" width="190" height="104" as="geometry"/>
    </mxCell>
    <mxCell id="c3" value="Kategoria" style="swimlane;html=1;startSize=26;" vertex="1" parent="1">
      <mxGeometry x="620" y="40" width="180" height="90" as="geometry"/>
    </mxCell>
    <mxCell id="c3a" value="+id: int&#10;+nazwa: string&#10;+maxDniWypozyczenia: int" style="text;html=1;align=left;verticalAlign=top;spacingLeft=4;" vertex="1" parent="c3">
      <mxGeometry y="26" width="180" height="64" as="geometry"/>
    </mxCell>
    <mxCell id="c4" value="Rezerwacja" style="swimlane;html=1;startSize=26;" vertex="1" parent="1">
      <mxGeometry x="40" y="240" width="180" height="100" as="geometry"/>
    </mxCell>
    <mxCell id="c4a" value="+id: int&#10;+dataOd: date&#10;+dataDo: date&#10;+status: StatusRezerwacji" style="text;html=1;align=left;verticalAlign=top;spacingLeft=4;" vertex="1" parent="c4">
      <mxGeometry y="26" width="180" height="74" as="geometry"/>
    </mxCell>
    <mxCell id="c5" value="Wypozyczenie" style="swimlane;html=1;startSize=26;" vertex="1" parent="1">
      <mxGeometry x="320" y="240" width="200" height="120" as="geometry"/>
    </mxCell>
    <mxCell id="c5a" value="+id: int&#10;+dataWydania: datetime&#10;+dataZwrotu: datetime&#10;+terminZwrotu: datetime&#10;+przeterminowane: bool" style="text;html=1;align=left;verticalAlign=top;spacingLeft=4;" vertex="1" parent="c5">
      <mxGeometry y="26" width="200" height="94" as="geometry"/>
    </mxCell>
    <!-- Relacje -->
    <mxCell id="r1" value="składa 1..*" style="endArrow=open;html=1;" edge="1" parent="1" source="c1" target="c4"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="r2" value="grupuje 1..*" style="endArrow=open;html=1;" edge="1" parent="1" source="c3" target="c2"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="r3" value="dotyczy 1..*" style="endArrow=open;html=1;" edge="1" parent="1" source="c2" target="c4"><mxGeometry relative="1" as="geometry"/></mxCell>
    <mxCell id="r4" value="realizuje 0..1" style="endArrow=open;html=1;" edge="1" parent="1" source="c4" target="c5"><mxGeometry relative="1" as="geometry"/></mxCell>
  </root>
</mxGraphModel>
```

## Eksport

Eksport do PNG/SVG: draw.io → File → Export as → PNG/SVG.
