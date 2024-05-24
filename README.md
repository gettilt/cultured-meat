<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Cultured Meat
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Cultured meat is the combination of multiple ingredients from other animals such as stem cells that are grown in a protein bath. Next 3D printing is used to shape the cellular growth. Any company working on cultured meats will win.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| ADM | Archer-Daniels-Midland provides essential ingredients and bioproducts for cultured meat production. | chat_gpt,google,claude |
| AMZN | Amazon's Whole Foods Market could be a major distributor of cultured meat products. | chat_gpt |
| BYND | Beyond Meat is a leader in plant-based meat alternatives and is investing in cultured meat technology. | chat_gpt,claude |
| DOW | Dow Inc. supplies biochemicals and materials that can be used in the production of cultured meat. | chat_gpt |
| KHC | Kraft Heinz is exploring alternative proteins and could incorporate cultured meat into its product lines. | chat_gpt,claude |
| MMM | 3M provides essential materials and technologies for 3D printing, crucial for shaping cultured meat. | chat_gpt |
| MSFT | Microsoft's cloud computing and AI capabilities support biotech research and development, including cultured meat. | chat_gpt |
| NDAQ | NASDAQ-listed companies are often at the forefront of biotech and food tech innovations, including cultured meat. | chat_gpt |
| TSN | Tyson Foods has invested in cultured meat startups and is exploring alternative protein sources. | chat_gpt,google,claude |
| BG | Bunge Limited, an agribusiness and food company, could supply plant-based oils and proteins for cultured meat production. | google,claude |
| FMC |  | google |
| SMG |  | google |
| HAIN | Hain Celestial, a leading organic and natural products company, could venture into the cultured meat space to expand its offerings. | claude |
| HRL | Hormel Foods, known for its meat products, could diversify its portfolio by investing in cultured meat technologies. | claude |
| INGR | Ingredion is a global ingredient solutions provider that could supply key components for cultured meat growth media. | claude |
| SMPL | The Simply Good Foods Company, known for its protein-rich snacks, could explore cultured meat as a new protein source. | claude |
| STKL | SunOpta is a plant-based food and beverage company that could leverage its expertise to enter the cultured meat market. | claude |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/cultured-meat/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/cultured-meat" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
