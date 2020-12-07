# linkedin-network-visualization
Visualize your LinkedIn connections in a network graph and see where your connections work.

[Live DEMO](https://thanh-to.github.io/linkedin-connections-visualization.html)

This is an entry to [HackCamp 2020](https://devpost.com/software/linkedin-connections-visualization).

## Inspiration
Throughout the ongoing COVID-19 pandemic, there have been many discussions on whether [COVID-19 is undoing diversity and inclusion efforts](https://techcrunch.com/2020/07/02/lets-stop-covid-19-from-undoing-diversity-gains/). With the new normal of working from home and social distancing, it has become incredibly difficult to expand your professional network. Those with less connections are finding it much more challenging to break into new circles, making those less diverse. To help other and myself break out of our own circles, I want to see opportunities to expand my network.

## What it does
linkedin-network-visualization takes your [exported connections data from LinkedIn](https://www.linkedin.com/help/linkedin/answer/66844/export-connections-from-linkedin) and render it into a node graph.

With the visualization, you can identify the companies where the majority of your connections are working to reach out for job opportunities, as well as those hidden small companies you never thought of.

## How I built it
The `connections.csv` file from LinkedIn is parsed in to an object and then rendered with [D3.js v4 Force Directed Graph with Labels](https://bl.ocks.org/heybignick/3faf257bbbbc7743bb72310d03b86ee8)

The nodes of the graph are generated from your connections.
The edges of the graph are generated for connections who work at the same company.

## Challenges I ran into
Initially, I wanted to use the [official LinkedIn Connections API](https://developer.linkedin.com/docs/v1/people/connections-api) to get a true connected graph with 1st and 2nd degree connections. Unfortunately, the API only retrieve basic profiles for 1st degree connections. It along with other LinkedIn API have also been deprecated for personal use and is only available to through the LinkedIn Partnership Program.

Then I found the [linkedin_api by tomquirk](https://github.com/tomquirk/linkedin-api). This is an attempt to provide a simple Python interface for the Linkedin API. It provides high level of details, including 2nd degree connection. The graph can be generated with this method be running `python with_linkedin_in/generate_linked_nodes_json.py` and open `with_linkedin_in/index.html`. However, this is an independent and unofficial API, thus violates Linkedin's User Agreement Section 8.2, and may result in an account ban.

Finally I settled with downloading and manipulating the [connections data provided by LinkedIn](https://www.linkedin.com/help/linkedin/answer/66844/export-connections-from-linkedin)

## What I learned
LinkedIn is incredibly restrictive on the use of their API

## Next Steps
Look into better ways to retreive LinkedIn connections data by applying to the LinkedIn Partnership Program

## References
[linkedin_api](https://github.com/tomquirk/linkedin-api)

[D3.js v4 Force Directed Graph with Labels](https://bl.ocks.org/heybignick/3faf257bbbbc7743bb72310d03b86ee8)
