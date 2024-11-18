# Advanced Tracking Templates & Implementation Guide

## Core Templates by Level

### Account Level Base Template
```
{lpurl}?utm_source=google
&utm_medium=paid_search
&account_id=[ACCOUNT_ID]
&network={network}
&campaign={campaignid}
&adgroup={adgroupid}
&keyword={keyword}
&matchtype={matchtype}
&creative={creative}
&placement={placement}
&target={target}
&device={device}
&devicemodel={devicemodel}
&loc_physical={loc_physical_ms}
&loc_interest={loc_interest_ms}
&gclid={gclid}
&extensionid={extensionid}
&feeditemid={feeditemid}
&targetid={targetid}
&user_language={user_language}
&random={random}
```

### Campaign Level - Enhanced
```
{lpurl}?utm_source=google
&utm_medium={ifcontent:display}{ifsearch:search}
&utm_campaign={campaignname}_{campaignid}
&utm_content={adgroupid}
&campaign_type={campaign_type}
&campaign_objective={campaign_objective}
&bidding_strategy={bidding_strategy_type}
&network={network}
&device={device}
&devicemodel={devicemodel}
&creative={creative}
&keyword={keyword}
&matchtype={matchtype}
&placement={placement}
&target={target}
&audience={targetid}
&loc_physical={loc_physical_ms}
&loc_interest={loc_interest_ms}
&feed_item={feeditemid}
&extension={extensionid}
&target_id={targetid}
&user_language={user_language}
&custom_param1={param1}
&custom_param2={param2}
&gclid={gclid}
&random={random}
```

### Dynamic Remarketing Enhancement
```
{lpurl}?utm_source=google
&utm_medium=remarketing
&utm_campaign={campaignname}
&utm_content={adgroupid}
&dynx_itemid={dynx_itemid}
&dynx_pagetype={dynx_pagetype}
&dynx_totalvalue={dynx_totalvalue}
&remarketing_list={targetid}
&audience_segment={audience}
&creative={creative}
&placement={placement}
&target={target}
&network={network}
&device={device}
&gclid={gclid}
```

### Video Campaign Specific
```
{lpurl}?utm_source=youtube
&utm_medium=video
&utm_campaign={campaignname}
&utm_content={adgroupid}
&video_id={creative}
&video_format={creative:format}
&video_position={adposition}
&skip_type={creative:skip}
&view_type={creative:view}
&placement_type={placement:type}
&channel_id={placement:channel}
&network=ytv
&device={device}
&devicemodel={devicemodel}
&targeting_type={target}
&audience={targetid}
&loc_physical={loc_physical_ms}
&loc_interest={loc_interest_ms}
&gclid={gclid}
```

### Performance Max Enhanced
```
{lpurl}?utm_source=google
&utm_medium=pmax
&utm_campaign={campaignname}
&utm_content={adgroupid}
&asset_group={adgroupid}
&pmax_placement={placement}
&listing_id={targetid}
&merchant_id={merchant_id}
&product_id={product_id}
&product_channel={product_channel}
&product_partition={product_partition_id}
&audience={targetid}
&creative={creative}
&device={device}
&network={network}
&loc_physical={loc_physical_ms}
&loc_interest={loc_interest_ms}
&gclid={gclid}
```

### Extended URL Parameters Format
```
// For single redirect
{lpurl}?param=value

// For double redirect (with third-party tracking)
{lpurl+2}%253Fparam=value

// For triple redirect (complex tracking chain)
{lpurl+3}%25253Fparam=value
```

## Critical Implementation Notes

1. URL Structure Priority:
```
Base Parameters:
- UTM Parameters (source, medium, campaign)
- Campaign Identifiers
- Ad Group / Creative Info
- Targeting Parameters
- Device / Network Info
- Location Data
- Click Identifiers (gclid)
```

2. Enhanced Conditional Logic:
```
Device Targeting:
{ifmobile:mobile_value}{ifnotmobile:desktop_value}

Network Targeting:
{ifsearch:search_value}{ifcontent:display_value}

Custom Logic:
{ifmobile:m}{ifnotmobile:d}/path?device={device}
```

3. Advanced Parameter Handling:
```
Parameter Escaping Rules:
- {lpurl} at start: Use ?
- {lpurl} mid-URL: Use %3F
- Double escape: %253F
- Triple escape: %25253F

Special Characters:
- Space replacement: %20
- Ampersand in final URL: &
- Ampersand in tracking template: %26
```

## Best Practices & Crucial Additions

1. Security Considerations:
```
- Always use HTTPS for base URLs
- Implement parameter validation
- Avoid PII in URL parameters
- Use {ignore} for non-critical parameters
```

2. Analytics Integration:
```
- Include GA4 compatible parameters
- Add cross-domain tracking parameters
- Implement conversion linker parameters
- Add session/user ID parameters when applicable
```

3. Error Prevention:
```
- Test all templates before deployment
- Verify parameter passing
- Check URL length (max 2048 characters)
- Monitor tracking implementation
- Use URL builder tools for validation
```

DISCLAIMER:
This guide represents a comprehensive but not exhaustive list of tracking implementations. Always:
- Test thoroughly in a controlled environment
- Verify compatibility with your analytics setup
- Monitor tracking performance regularly
- Keep backup of original URLs
- Follow Google Ads' latest guidelines
- Consider privacy regulations and compliance
- Review implementation quarterly

Key Updates & Maintenance:
- Check Google Ads documentation monthly for parameter updates
- Verify tracking functionality after platform updates
- Monitor conversion tracking accuracy
- Update templates based on performance data
- Document all custom implementations

Reference URL: https://support.google.com/google-ads/answer/6305348?hl=en#zippy=%2Cfinal-url-tracking-template-or-custom-parameter%2Ctracking-template-only%2Cfinal-url-only%2Cshopping-campaigns-only%2Cvideo-campaigns-only%2Chotel-campaigns-only%2Cdemand-gen-ads-campaigns%2Cperformance-max-campaigns%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-dynamic-ad-targets-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-keywords-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-sitelink-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ads-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ad-group-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-campaign-level
