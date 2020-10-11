# Table of contents
- [First setup](#first-setup)
- [Start from scratch](#start-scratch)
- [Scrape products](#scrape-products)
- [Adding products](#adding-products)
    - [Links to scrape from](#links-to-scrape-from)
    - [Optional arguments](#optional-arguments)

<br/>

## First setup <a name="first-setup"></a>
Make sure you have the modules, run this in the terminal:

    pip install -r requirements.txt

## Start from scratch <a name="start-scratch"></a>
If you want to start from scratch with no data in the records.json file, then just delete all the content in records.json apart from two curly brackets:

    {}

Then delete the lines under the last if-statement in scraper.py. 

Then just add products like described [here](#add-products).

## Scrape products <a name="scrape-products"></a>
To scrape prices of products run this in the terminal:

    python3 scraper.py

## Add products <a name="add-products"></a>
Before scraping a new product, run a similar line to this:

    python3 add_product.py <category> <url>
e.g.

    python3 add_product.py gpu https://www.komplett.dk/product/1135037/hardware/pc-komponenter/grafikkort/msi-geforce-rtx-2080-super-gaming-x-trio

This adds the category (if new) and the product to the records.json file, and adds a line at the end of the scraper.py file so the script can scrape price of the new product.

**OBS**: The category can only be one word, so add a underscore instead of a space if needed.<br/>
**OBS**: The url must have the "https://www." part.<br/>
**OBS**: When using Amazon links, delete everything after and including this "ref=sr".<br/>
For example the link: https://www.amazon.com/NVIDIA-GEFORCE-RTX-2080-Founders/dp/B07HWMDDMK/ref=sr_1_2?dchild=1&qid=1601488833&s=computers-intl-ship&sr=1-2<br/>
Should be: https://www.amazon.com/NVIDIA-GEFORCE-RTX-2080-Founders/dp/B07HWMDDMK/<br/>
**OBS**: When using eBay links, delete everything after and including this "?_trkparms="<br/>
For example the link: https://www.ebay.com/itm/Samsung-Galaxy-Note-20-Ultra-256GB-12GB-RAM-SM-N986B-DS-FACTORY-UNLOCKED-6-9/193625604205?_trkparms=aid%3D111001%26algo%3DREC.SEED%26ao%3D1%26asc%3D225074%26meid%3Dd6c93f1458884e65bcc434e38f6f303c%26pid%3D100970%26rk%3D8%26rkt%3D8%26mehot%3Dpp%26sd%3D402319206529%26itm%3D193625604205%26pmt%3D0%26noa%3D1%26pg%3D2380057%26brand%3DSamsung&_trksid=p2380057.c100970.m5481&_trkparms=pageci%3A6ffa204c-042b-11eb-baa4-3a1cc2bb9aea%7Cparentrq%3Ae60676341740a4d6b1579293fff1b710%7Ciid%3A1<br/>
Should be: https://www.ebay.com/itm/Samsung-Galaxy-Note-20-Ultra-256GB-12GB-RAM-SM-N986B-DS-FACTORY-UNLOCKED-6-9/193625604205

### Links to scrape from <a name="links-to-scrape-from"></a>
The tech scraper can scrape prices on products from:
- [Komplett.dk](https://www.komplett.dk/)
- [Proshop.dk](https://www.proshop.dk/)
- [Computersalg.dk](https://www.computersalg.dk/)
- [Elgiganten.dk](https://www.elgiganten.dk/)
- [AvXperten.dk](https://www.avxperten.dk/)
- [Av-Cables.dk](https://www.av-cables.dk/)
- [Amazon.com](https://www.amazon.com/)
- [eBay.com](https://www.ebay.com/)
- [Power.dk](https://www.power.dk/)
- [Expert.dk](https://www.expert.dk/)
- [MM-Vision.dk](https://www.mm-vision.dk/)
- [Coolshop.dk](https://www.coolshop.dk/)
- [Sharkgaming.dk](https://www.sharkgaming.dk/)

### Optional arguments <a name="optional-arguments"></a>
There is some optional arguments you can use when running add_product.py, these are:

-     --komplett

-     --proshop

-     --computersalg

-     --elgiganten

-     --avxperten

-     --avcables

-     --amazon

-     --ebay

-     --power

-     --expert

-     --mmvision

-     --coolshop

-     --sharkgaming

When using one or more of "domain" arguments, only the chosen domains gets added to records.json under the product name. 