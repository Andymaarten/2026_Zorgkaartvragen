# Changelog aandachtspunten.json v5.0 (13-10-2026)

Basis: v4.0 (12-10-2026) en BRIEFING_aandachtspunten_v5.md. Ids, volgorde, labels en categorieën ongewijzigd. Bron: `261013_Prompts_aandachtspunten_v5.0.xlsx` → `build_aandachtspunten_json.py`.

## Algemeen

- `betekenis` van alle 88 AP's herschreven (§4): per passage beoordeelbaar, ontkenning expliciet, over wie, periode, grenswaarden als getallen, geen halve treffers. Mediaan 485 tekens; 9 AP's >600 (de 5 samengestelde omdat call 1 de factorlijst nodig heeft, plus AP063, AP075, AP082, AP088 net erboven).
- Nieuwe velden: `factoren` (tekst), `toetsregels` (tekst, niet door code gebruikt), `samengesteld` (bool), `familie_telt` (bool).
- Zoekwoorden: kapotte patronen `[p2`/`3]` (AP022, AP055) en `[p97`/`7]` (AP064) vervangen door `[p2,3]`/`[p2.3]` en `[p97,7]`/`[p97.7]`; de generator splitst niet meer op komma's binnen `[ ]`. Woordfamilies toegevoegd (o.a. AP077 `[NL]`, anderstalig, engelstalig, nederlandstalig, taalbarrière, beheerst; AP022/AP064 `[gew]`, geb.gew, geboortegew, `[GG]`; AP069 rook/gerookt/roker/smok/vape…). Eerdere kolom 'extra' samengevoegd. Geen AP zonder zoekwoorden (min 9, max 48).
- Velden `zoek_naar`, `blokken`, `python_regel` staan er nog maar worden niet gebruikt (§3).

## samengesteld = true

AP001, AP052, AP053, AP079, AP081

## familie_telt = true

AP001, AP052, AP053, AP081 (eerstegraads: ouder, broer/zus, kind)

## Per AP

- **AP001 Risicofactoren pre-eclampsie (Ascal)**: Tel- en toetsregels naar `toetsregels`; factorlijst in `factoren` (zonder 'alleen als samenhang blijkt'); samengesteld, familie telt (moeder/zus).
- **AP002 Asfyxie of perinatale sterfte in anamnese**: Over wie (eerder kind) en periode expliciet; grens 22+0 als getal; uitsluitingen compact.
- **AP003 Asherman in anamnese**: Ingekort; normale hysteroscopie als ontkenning toegevoegd.
- **AP004 Bariatrische chirurgie i.a. BMI 30-40**: Geen halve treffers: BMI alleen is nooit positief; operatie is de kernvoorwaarde.
- **AP005 Bariatrische chirurgie i.a. BMI >40**: Zie AP004.
- **AP006 Bariatrische chirurgie i.a. BMI <30**: Zie AP004 (dit was het gemelde geval 'BMI 23.7' zonder operatie).
- **AP007 Schouderdystocie in anamnese**: Ingekort; over wie/periode expliciet.
- **AP008 SSRI-gebruik**: Ontkenning/gestopt expliciet; periode huidig.
- **AP009 (Sub)totaalruptuur in anamnese**: Ingekort; graad als getal; uitsluitingen expliciet.
- **AP010 Obesitas BMI tussen 30 en 35**: Getallen expliciet; periode (intake) expliciet.
- **AP011 Obesitas met BMI 35 tot onder 40**: Zie AP010.
- **AP012 Obesitas BMI >40**: Zie AP010.
- **AP013 Chronische hypertensie**: Periode en ontkenning (normale RR) expliciet; grens 20+0.
- **AP014 Conisatie in anamnese**: Ingekort; gepland/normaal als ontkenning.
- **AP015 COPD of astma**: Ontkenning en familie expliciet; ernst blijft bij de zorgverlener (besluit 9-10).
- **AP016 Colitis ulcerosa of ziekte van Crohn met medicatie**: Medicatiepassage telt op zichzelf (geen halve treffer); ontkenning expliciet.
- **AP017 Pre-existente diabetes mellitus**: Periode (vóór de zwangerschap) en ontkenning expliciet.
- **AP018 Diabetes gravidarum in anamnese**: Periode (eerdere zwangerschap) en ontkenning expliciet.
- **AP019 Diabetes gravidarum in de huidige zwangerschap**: Periode (huidig) en normale uitslag/aanvraag als ontkenning expliciet; grenzen als getallen.
- **AP020 Harddrugsgebruik**: Ontkenning expliciet; periode 'ook verleden' (besluit 9-10).
- **AP021 Softdrugsgebruik**: Ontkenning en periode expliciet.
- **AP022 Dysmaturiteit in anamnese**: Kapot patroon '[p2'/'3]' vervangen door [p2,3]/[p2.3]; gewichtsafkortingen ([gew], geb.gew, [GG]) toegevoegd; ontkenning expliciet.
- **AP023 Epilepsie met medicatie**: Medicatiepassage telt op zichzelf; ontkenning expliciet.
- **AP024 Ernstige pre-eclampsie of HELLP vóór 34 weken in anamnese**: Grens 34+0 als getal; ontkenning expliciet.
- **AP025 Eerder kind met GBS-ziekte**: Over wie (eerder kind) expliciet.
- **AP026 GBS-urie in de huidige zwangerschap**: Periode en ontkenning (negatieve kweek) expliciet.
- **AP027 Bichoriale gemelli**: Afspraak 9-10 behouden; ingekort.
- **AP028 Monochoriale gemelli**: Ingekort.
- **AP029 Hepatitis B-dragerschap**: Negatieve uitslag en familie als ontkenning expliciet.
- **AP030 Herhaalde miskramen vanaf drie**: Getal expliciet; ingekort.
- **AP031 HIV**: Negatieve test en partner als ontkenning.
- **AP032 Hyperthyreoïdie in anamnese met positieve TSHRAb**: Hyper/hypo, anamnese/huidig en met/zonder antistoffen scherp; normale uitslag en aanvraag niet positief.
- **AP033 Huidige hyperthyreoïdie met positieve TSHRAb**: Idem AP032, periode huidig.
- **AP034 Hyperthyreoïdie in anamnese zonder bekende positieve TSHRAb**: Idem AP032; 'schildklierafwijking' zonder richting niet positief.
- **AP035 Hypothyreoïdie in anamnese**: Idem AP032; normale uitslag/aanvraag niet positief.
- **AP036 Huidige hypothyreoïdie**: Idem AP032, periode huidig.
- **AP037 Zwanger na fertiliteitsbehandeling**: 'Spontaan zwanger' als ontkenning; ingekort.
- **AP038 Klinisch relevante irregulaire antistoffen**: Negatieve screening expliciet niet positief.
- **AP039 Niet klinisch relevante irregulaire antistoffen variant 1**: Ingekort.
- **AP040 Jehovah’s Getuige of weigering van bloedproducten**: Ingekort; akkoord-met-bloed als ontkenning.
- **AP041 LLETZ in anamnese**: Ingekort.
- **AP042 Lithiumgebruik**: Gestopt als ontkenning expliciet.
- **AP043 MPV of HPP in anamnese**: Getal expliciet; 'normaal bloedverlies' als ontkenning.
- **AP044 Ondergewicht BMI <18.5**: Getal expliciet (het gemelde 18,69-geval).
- **AP045 Uterus myomatosus**: Ontkenning expliciet; ingekort.
- **AP046 Vaginisme**: Ingekort.
- **AP047 Vroeggeboorte <34w in anamnese**: Grens 34+0 expliciet (34+6 valt onder AP050).
- **AP048 Vluchteling/asielzoeker**: Ingekort.
- **AP049 Maternale leeftijd >40 jaar**: Getal en referentiedatum expliciet.
- **AP050 Vroeggeboorte >34w in anamnese**: Grenzen 34+0 en 37+0 expliciet.
- **AP051 Zwangerschap na eiceldonatie**: Ingekort.
- **AP052 Trombose en trombofilie (profylaxe zwangerschap en kraambed)**: Factorlijst in `factoren`, protocolregels in `toetsregels`; samengesteld, familie telt (eerstegraads).
- **AP053 Trombose en trombofilie (profylaxe kraambed)**: Idem AP052, kraambed-variant; tabel-4-regels in `toetsregels`.
- **AP054 Sectio in anamnese**: Strikt: alleen uitgevoerde sectio (besluit 9-10); ingekort.
- **AP055 Verdenking FGR in de huidige zwangerschap**: Kapot patroon gerepareerd; normale groei als ontkenning.
- **AP056 Anemie of ijzertekort**: Periode (huidig; geen Hb van na een vorige bevalling) en normale waarde expliciet.
- **AP057 Rhesus D-negatief**: 'O pos' expliciet niet positief.
- **AP058 Rhesus c-negatief**: Ingekort; D-status als ontkenning.
- **AP059 Zwangerschapsinterval <1 jaar**: Geformuleerd met datums (AD − 266 dagen); grootste ruisbron.
- **AP060 Zwangerschapscholestase**: Normale/aangevraagde galzuren als ontkenning.
- **AP061 PCOS**: Ingekort.
- **AP062 Pre-eclampsie in de huidige zwangerschap**: Normaal toxlab/'geen PE' als ontkenning; periode expliciet.
- **AP063 Zwangerschapshypertensie (PIH)**: Normale RR als ontkenning; getallen expliciet.
- **AP064 Macrosomie of LGA in anamnese**: Kapot patroon '[p97'/'7]' vervangen door [p97,7]/[p97.7]; gewichtsafkortingen toegevoegd.
- **AP065 Therapeutische antistolling tijdens zwangerschap of kraambed**: Profylactisch als ontkenning; ingekort.
- **AP066 Antifosfolipidensyndroom (APS)**: Negatieve screening als ontkenning.
- **AP067 Niet klinisch relevante irregulaire antistoffen variant 2**: Gelijk aan AP039 (duplicaat, bewust behouden).
- **AP068 Gebruik van TNF-alfa-remmers**: Besluit 9-10 behouden; ingekort.
- **AP069 Roken in de zwangerschap**: Ontkenning bij de zwangere expliciet niet positief ('Tabak niet gerookt'); woordfamilie uitgebreid.
- **AP070 Velamenteuze navelstrenginsertie met vasa praevia uitgesloten**: Twee voorwaarden benoemd; ingekort.
- **AP071 Congenitale uterusanomalie**: Ingekort; normale echo als ontkenning.
- **AP072 Trombocytopenie**: Getal en periode expliciet.
- **AP073 Langdurig/prematuur gebroken vliezen (PROM/PPROM)**: Ontkenning ('vliezen staan', negatieve test) expliciet.
- **AP074 Ehlers-Danlos of hypermobiliteitssyndroom**: Ingekort.
- **AP075 Placenta praevia**: Afstand als getal; 'voorwand/achterwand' expliciet niet positief.
- **AP076 Laagliggende placenta**: Afstand als getal; 'voorwand/achterwand' expliciet niet positief.
- **AP077 Taalbarrière**: Woordfamilie uit §6 toegevoegd; 'spreekt goed Nederlands' als ontkenning.
- **AP078 Engelstalige communicatie**: Ingekort.
- **AP079 Mogelijke kwetsbaarheden in de zwangerschap**: Lijst in `factoren`; samengesteld; 'geen bijzonderheden' als ontkenning. Vraag: telt de partner mee (geweld, drugs)?
- **AP080 Algemene schildklierproblemen**: Normale uitslag en aanvraag niet positief (§5).
- **AP081 Risicofactoren diabetes gravidarum**: Factorlijst in `factoren` met eerstegraads familie expliciet ('diabetes: vader van mw'); samengesteld, familie telt.
- **AP082 Hyperemesis gravidarum in de huidige zwangerschap**: Besluit 9-10 behouden; ontkenning toegevoegd.
- **AP083 Herpes genitalis primo-infectie in de huidige zwangerschap**: Koortslip en HSV-1-serologie expliciet niet positief (§5).
- **AP084 Recidief herpes genitalis in de huidige zwangerschap**: Koortslip en serologie expliciet niet positief (§5).
- **AP085 Acute fatty liver of pregnancy in anamnese**: Ingekort.
- **AP086 Systemische lupus erythematodes met of zonder positieve ENA**: Ingekort.
- **AP087 ABO-bloedgroepantagonisme in anamnese**: Ingekort.
- **AP088 Congenitale afwijking bij eerder kind**: Ingekort; 'gezond kind' als ontkenning. Open vraag (miskraam met chromosoomafwijking) blijft.

## Open vragen aan Andreas

1. **Familiefilter en 'eerder kind'.** Het Python-filter verwijdert passages over partner of familie. Passages over een eerder kind (AP002, AP007, AP009, AP022, AP025, AP043, AP064, AP087, AP088) mogen daar niet onder vallen. Klopt dat in de code?
2. **AP079 en de partner.** Huiselijk geweld of drugsgebruik door de partner is relevant voor kwetsbaarheid. Nu `familie_telt = false`. Moet dat `true`, of een apart partnerfilter?
3. **AP004–006 en AP070 (twee voorwaarden).** In call 2 kan één passage niet beide voorwaarden bevatten. Gekozen: de operatie-/insertiepassage is positief, de BMI-band resp. 'vasa praevia uitgesloten' combineert de zorgverlener (en Python filtert BMI). Akkoord? Past de Python-BMI-lijst de band toe bij AP004/005/006?
4. **AP016 en AP023 (ziekte met medicatie).** Gekozen: een passage met alleen het medicijn telt (impliceert behandelde ziekte). Akkoord?
5. **AP052/AP053 familieanamnese.** Gekozen: eerstegraads (ouder, broer/zus, kind). Het protocol noemt bij sterke trombofilie 'familieanamnese' zonder graad. Eerstegraads aanhouden?
6. **AP067** blijft een duplicaat van AP039 (bewust, conform besluit 12-10). Laten staan?
7. **AP088**: telt een spontane miskraam met aangetoonde chromosoomafwijking mee, en dragerschap bij de partner? Nu: miskraam met chromosoomafwijking ja (in zoekwoorden en betekenis), dragerschap zonder aangedaan kind nee.
8. **Zoekwoorden, hoofdlettergevoeligheid.** Korte afkortingen in gemengde kast zoals `[Ht]`, `[Tr]`, `[Fe]`, `[Rh]`: hoofdlettergevoelig of niet? En wordt `[p2,3]` in de code als één patroon gelezen (de json bevat het nu als één item)?
9. **Labels.** Ongewijzigd t.o.v. v4.0 (dus de vier hernoemde labels van 12-10 blijven: AP001, AP052, AP053, AP081).
