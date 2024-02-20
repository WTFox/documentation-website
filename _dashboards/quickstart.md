---
layout: default
title: OpenSearch Dashboards quickstart
nav_order: 2
has_children: false
redirect_from:
   - /dashboards/quickstart-dashboards/
---

# OpenSearch Dashboards quickstart

Get started with OpenSearch Dashboards. This guide covers the basics like:

- **Adding sample data:** Get started with pre-loaded visualizations, dashboards, and other tools to help you explore OpenSearch Dashboards before you add your own data.
- **Exploring your data:** Dig into your data and see what is there.
- **Creating visualizations:** Make your data more accessible by creating visualizations.

Starting with OpenSearch 2.13, you'll see the following homepage view. Your view can be in either [light or dark mode](<insert-link>), depending on your admin settings. The OpenSearch Dashboards redesign considers the community's feedback on simplifying user experience. Share your [feedback](<insert-link-feedback-dashboards>) about the redesign or other tools you want to see in OpenSearch Dashboards.

<img src="{{site.url}}{{site.baseurl}}/images/dashboards/dashboards-home.png" alt="Screenshot of OpenSearch Dashboards homepage" width="700">

## Prerequisites

Before getting started with this guide, make sure you have installed the latest version of OpenSearch and OpenSearch Dashboards. If you are running OpenSearch 2.11 or earlier, certain features in this guide are not available in those versions. See your version's respective documentation for more information.

For information about installation and configuration, see [Install and configure OpenSearch]({{site.url}}{{site.baseurl}}/install-and-configure/install-opensearch/index/) and [Install and configure OpenSearch Dashboards]({{site.url}}{{site.baseurl}}/install-and-configure/install-dashboards/index/). 

The following sections include tutorials on OpenSearch basics. Use your own environment or the [OpenSearch Playground](https://playground.opensearch.org/app/home#/), which runs on the latest version of OpenSearch. 

## Adding sample data

To add sample data, follow these steps:

1. On the OpenSearch Dashboards **Home** page, choose **Add data** on the upper-right side of the page.
2. On the **Add sample data** page, choose the datasets you want to add.

The [**Sample flight data** dataset](https://playground.opensearch.org/app/home#/tutorial_directory) is used in the tutorials in this quickstart.
{: .note}

The following image shows a view of the adding sample data window.

<img src="{{site.url}}{{site.baseurl}}/images/dashboards/add-sample-data-2.png" alt="Adding sample data window" width="700">

## Exploring data using Discover

In [**Discover**]({{site.url}}{{site.baseurl}}/dashboards/discover/index-discover/), you can: 

- Choose data to explore, set a time range for that data, search it using [Dashboards Query Language (DQL)]({{site.url}}{{site.baseurl}}/dashboards/dql/), and filter the results.
- Analyze your data by querying and filtering, viewing results in a table, and examining documents.
- Display the distribution of your data in histograms.

The following steps give you a basic overview about using the Discover tool:

1. From the OpenSearch Dashboards navigation menu, choose **Discover**. 
2. On the **Discover** page, choose the sample flight dataset from the dropdown menu on the upper-left side of the page. 
3. Select the calendar icon to change the [time filter]({{site.url}}{{site.baseurl}}/dashboards/discover/time-filter/) from the default of **Last 15 minutes** to **Last 7 days**.
4. In the DQL search bar, input `FlightDelay:true AND DestCountry: US AND FlightDelayMin >= 60` and then select **Update**. Results for US-bound flights delayed by 60 minutes or more are shown.
5. Filter data by choosing **Add filter** from under the DQL search bar and then selecting an **Available field**. For example, select `FlightDelayType`, **is**, and **Weather Delay** from the **Field**, **Operator**, and **Value** dropdown lists on the **Edit Filter** pop-up window.

The following image shows the view you see once you have completed the preceding steps.

<img src="{{site.url}}{{site.baseurl}}/images/dashboards/discover-view.png" alt="Discover tutorial screen view" width="700">

## Visualizing data using Dashboards

You can do the following in **Dashboards**:

- Display data in a single view.
- Build dynamic dashboards.
- Create and share reports.
- Embed analytics to differentiate your applications.

The following steps give you a basic overview about using the Dashboard tool:

1. On the OpenSearch Dashboards **Home** page, choose **Dashboards** .
2. From the search toolbar, search for **[Flights] Global Flight Dashboard** and then select it. You'll see a pre-loaded dashboard with visuals, including charts, maps, and data tables. 
3. To add other panels to the dashboard, select the **Edit** button and then choose **Add** from the toolbar. The **Add panels** window then opens. 
4. From the search toolbar in the **Add panels** window, search for the existing panel **[Flights] Delay Buckets** and then select it. A pop-up message confirms that you've added the panel.
5. Select close `x` to exit the **Add panels** window.
6. View the newly added panel, **[Flights] Delay Buckets**, at the end of the dashboard.

The following image shows the view you see once you have completed the preceding steps.

<img src="{{site.url}}{{site.baseurl}}/images/dashboards/add-panel2.png" alt="Add panel tutorial screen view" width="700">

Continuing with the preceding dashboard, you will create a bar chart comparing the number of canceled flights and delayed flights to delay type and then add the panel to the dashboard:

1. Change the default [time range]({{site.url}}{{site.baseurl}}/dashboards/discover/time-filter/) from **24 hours** to **Last 7 days**. 
2. In the toolbar, choose **Edit**, then **Create new**.
3. Select **VisBuilder** in the **New Visualizations** window.
4. In the **Data Source** dropdown list, choose `opensearch_dashboards_sample_data_flights`.
5. Drag the fields **Cancelled** and **FlightDelay** to the y-axis column.
6. Drag the field **FlightDelayType** to the x-axis column.
7. Choose **Save** and name the visualization in the **Title** field.
8. Choose **Save and return**. A bar chart is added as the last panel on the dashboard.

The following image shows the view you see once you have completed the preceding steps.

<img src="{{site.url}}{{site.baseurl}}/images/<insert image>" alt="Dashboard tutorial panel view" width="700">

## Interacting with data using Dashboards

Interactive dashboards allow you to analyze data in more depth and filter it in several ways. With **Dashboards**, you can interact directly with data through the use of dashboard-level filters.

Take your previous dashboard and follow these steps to further analyze and filter the sample flight data:

1. On the **[Flights] Airline Carrier** panel, choose **OpenSearch-Air**. The dashboard updates automatically.
2. Choose **Save** to save the customized dashboard.

Another option is to use the dashboard toolbar to apply filters. Follow these steps to learn about this feature:

1. In the dashboard toolbar, choose **Add filter**.
2. From the **Field**, **Operator**, and **Value** dropdown lists, choose **Carrier**, **is**, and **OpenSearch-Air**, respectively, as shown in the following image.
3. Choose **Save**. The dashboard updates automatically.

The following image shows the view you see once you have completed the preceding steps.

<img src="{{site.url}}{{site.baseurl}}//images/<insert image>" alt="Screenshot of Dashboard tutorial panel view" width="700">

## Turning on and off dark mode

Turning on and off dark mode in OpenSearch Dashboards requires administrative access. If you are an administrator, follow these steps:

1. Navigate to **Management** > **Dashboards Management** > **Advanced Settings**.
2. Scroll down to the **Appearance** section and locate the **Dark mode** option.
3. Use the toggle switch to turn on or turn off dark mode for all users of your OpenSearch Dashboards instance.
4. Select the **Save changes** button and then the **Reload** button. Changes take effect immediately, so you will see the updated theme right away, similar to the view shown in the following image.

<img src="{{site.url}}{{site.baseurl}}/images/dashboards/dark-mode.png" alt="Dark mode view" width="700">

# Next steps

- **Visualize data.** To learn more about data visualizations in OpenSearch Dashboards, go to [Building data visualizations]({{site.url}}{{site.baseurl}}/dashboards/visualize/viz-index/).
- **Create dashboards.** To learn more about creating dashboards in OpenSearch Dashboards, go to [Creating dashboards]({{site.url}}{{site.baseurl}}/dashboards/quickstart-dashboards/).
- **Explore data.** To learn more about exploring data in OpenSearch Dashboards, go to [Exploring data]({{site.url}}{{site.baseurl}}/dashboards/discover/index-discover/). 
- **Ingest data.** To learn more about ingesting data in OpenSearch, go to [Ingest APIs]({{site.url}}{{site.baseurl}}/api-reference/ingest-apis/index/) and [Ingest pipelines]({{site.url}}{{site.baseurl}}/ingest-pipelines/).
