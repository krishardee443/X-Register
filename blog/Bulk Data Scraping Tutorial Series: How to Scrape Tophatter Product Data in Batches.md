# Bulk Data Scraping Tutorial Series: How to Scrape Tophatter Product Data in Batches

Bulk data scraping for cross-border e-commerce has been a hot topic discussed in my previous blogs. This efficient and powerful method allows users to scrape an entire platform’s product data in bulk, process it, and then re-upload it to another platform. Bulk scraping is widely used not only for collecting product information but also for batch submission or updates of data, enabling many unexpected and effective applications when combined with specific environments.

![Bulk Data Scraping Example](https://www.chenfeiblog.com/wp-content/uploads/2018/03/meeting-peoples-752x440.png)

Scraping isn't a mysterious technology; there are numerous ways to achieve it. For programmers, Python is the go-to option for its flexibility and powerful libraries. However, not everyone can master Python easily. This is why many rely on third-party tools for data scraping.

## Introduction to the Tutorial Series

To make this practical, I am starting a bulk data scraping tutorial series focusing on various cross-border e-commerce platforms. Platforms such as Amazon, eBay, AliExpress, Wish, Lazada, Cdiscount, Tophatter, Newegg, Shopee, Walmart, Tradera, Etsy, and Joom will be covered. Each article will demonstrate scraping techniques specific to one platform. Given the technical limitations of many sellers, this series will use the third-party scraping software **Web Scraper** for demonstrations, paired with graphical guides and videos.

The text content will be free for all readers, while videos will serve as supplementary material accessible only to paying members.

---

**Stop wasting time on proxies and CAPTCHAs! ScraperAPI's simple API handles millions of web scraping requests, so you can focus on the data. Get structured data from Amazon, Google, Walmart, and more. Start your free trial today! 👉 [https://www.scraperapi.com/?fp_ref=coupons](https://www.scraperapi.com/?fp_ref=coupons)**

---

## Why Start with Tophatter?

Starting April 1st, Tophatter has launched its **Seller Standards Program** and **Top Seller Program** ([source](https://www.cifnews.com/article/33730)). In this article, we’ll cover step-by-step how to scrape product data from Tophatter using scraping tools and techniques.

---

## Step 1: Analyze Tophatter’s Website Structure

Open the Tophatter website and identify the patterns and structures of the product listings. The scraping process generally starts by locating the product listing pages and then navigating to individual product detail pages.

![Tophatter Example](https://www.chenfeiblog.com/wp-content/uploads/2018/03/top1-800x467.png)

By clicking on the **Browse** link on the homepage, you’ll land on the product category pages, which act as the product listing pages.

### Key Observations:
1. Viewing the page source (right-click > "View Source") reveals no direct product-related information.
2. Modern websites often store product data in JSON objects loaded asynchronously via AJAX. Scraping such data requires finding the relevant JSON links in the **XHR** section of your browser’s developer tools (F12).

---

**Stop wasting time on proxies and CAPTCHAs! ScraperAPI's simple API handles millions of web scraping requests, so you can focus on the data. Get structured data from Amazon, Google, Walmart, and more. Start your free trial today! 👉 [https://www.scraperapi.com/?fp_ref=coupons](https://www.scraperapi.com/?fp_ref=coupons)**

---

### Example: Finding the JSON Data

1. Open Chrome Developer Tools (F12).
2. Refresh the product list page and check the **XHR** section.
3. Locate a suspicious JSON data packet. Copy its link and open it in your browser. The data will appear as raw JSON content, similar to the example below:

![JSON Data Example](https://www.chenfeiblog.com/wp-content/uploads/2018/03/top3-800x411.png)

For better readability, copy the content into a tool like [JSON.cn](https://www.json.cn) to format it. Here, you’ll find details like product IDs, prices, ratings, dimensions, and more.

---

## Step 2: Setting Up the Scraper

For demonstration, we’ll use **Web Scraper** to scrape Tophatter product data.

### Linking Listing Pages to Detail Pages

- **Listing Page URL Example**: `https://tophatter.com/api/v1/catalogs/9180/retrieve.json?per_page=50&page=2`
  - `per_page=50`: Fixed number of products per page.
  - `page=2`: Indicates the page number. Increment this value to scrape more pages.

- **Detail Page URL Example**: `https://tophatter.com/api/v1/lots/61057684?source=catalog-9180`
  - The product ID links listing pages to detail pages.

### Configuring Web Scraper

1. Create a new task in Web Scraper.
2. Replace the **page=2** parameter with a dynamic variable to scrape multiple pages.
3. Preview the listing pages to ensure the scraper detects the correct product links.

![Web Scraper Setup](https://www.chenfeiblog.com/wp-content/uploads/2018/03/top7.png)

---

## Step 3: Extracting Product Data

Using JSON extraction is the most efficient way to scrape structured data.

### Example: Extracting the Product Title

1. In Web Scraper, create a new field named `title`.
2. Use the JSON extraction option and input the JSON URL or paste the raw JSON content.
3. Select the **title** field from the formatted JSON view.

![JSON Extraction Example](https://www.chenfeiblog.com/wp-content/uploads/2018/03/top12.png)

Run a test scrape to verify the data:

![Scraping Result](https://www.chenfeiblog.com/wp-content/uploads/2018/03/top13-800x136.png)

---

## Step 4: Saving Scraped Data

Save the scraped data in your preferred format (e.g., CSV, JSON). Configure the output settings in Web Scraper to organize and store the data efficiently.

![Save Data Example](https://www.chenfeiblog.com/wp-content/uploads/2018/03/top14.png)

---

## Final Tips and Summary

This tutorial demonstrated how to scrape product data from Tophatter using JSON extraction. While we focused on scraping the **title**, the same method applies to extracting other fields like descriptions, prices, images, and ratings.

### Important Notes:
- Avoid overloading scraping tools; reduce scraping speed to avoid detection.
- Bulk scraping is powerful but should be used responsibly. Misuse can lead to account bans or other issues.
- For a more seamless scraping experience, consider using **ScraperAPI**, which handles CAPTCHAs, proxies, and JavaScript-heavy pages effortlessly.

---

**Stop wasting time on proxies and CAPTCHAs! ScraperAPI's simple API handles millions of web scraping requests, so you can focus on the data. Get structured data from Amazon, Google, Walmart, and more. Start your free trial today! 👉 [https://www.scraperapi.com/?fp_ref=coupons](https://www.scraperapi.com/?fp_ref=coupons)**

---

**Watch the video tutorial**: Learn more by watching the video demonstration on [YouTube](https://www.youtube.com/channel/UCOlOp1y3MMVDGaAmYwiUIMg?sub_confirmation=1).
