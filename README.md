# Cross-Platform Tracking Template Guide

## Table of Contents
1. Google Ads
2. Microsoft Ads (Bing)
3. Facebook/Instagram Ads
4. TikTok Ads
5. LinkedIn Ads
6. Outbrain
7. Taboola
8. Pinterest Ads
9. Snapchat Ads
10. Implementation Guide

## 1. Google Ads

### Account Level
```
{lpurl}?utm_source=google&utm_medium=cpc&utm_campaign={campaignid}&utm_content={adgroupid}&device={device}&devicemodel={devicemodel}&creative={creative}&keyword={keyword}&placement={placement}&target={target}&matchtype={matchtype}&network={network}&campaignid={campaignid}&adgroupid={adgroupid}&gclid={gclid}
```

### Campaign Level
```
{lpurl}?utm_source=google&utm_medium=cpc&utm_campaign={campaignname}&campaign_id={campaignid}&utm_content={adgroupid}&device={device}&campaign_type={campaign_type}&network={network}&matchtype={matchtype}&creative={creative}&keyword={keyword}&placement={placement}&target={target}&gclid={gclid}
```

### Ad Group Level
```
{lpurl}?utm_source=google&utm_medium=cpc&utm_campaign={campaignname}&utm_adgroup={adgroupname}&adgroup_id={adgroupid}&device={device}&keyword={keyword}&creative={creative}&matchtype={matchtype}&placement={placement}&target={target}&network={network}&gclid={gclid}
```

## 2. Microsoft Ads (Bing)

### Account Level
```
{lpurl}?utm_source=bing&utm_medium=cpc&utm_campaign={campaignid}&utm_content={adgroupid}&device={device}&keyword={keyword}&matchtype={matchtype}&target={target}&network={network}&msclkid={msclkid}
```

### Campaign Level
```
{lpurl}?utm_source=bing&utm_medium=cpc&utm_campaign={campaignname}&campaign_id={campaignid}&device={device}&network={network}&matchtype={matchtype}&keyword={keyword}&msclkid={msclkid}
```

### Ad Group Level
```
{lpurl}?utm_source=bing&utm_medium=cpc&utm_campaign={campaignname}&utm_adgroup={adgroupname}&adgroup_id={adgroupid}&device={device}&keyword={keyword}&matchtype={matchtype}&msclkid={msclkid}
```

## 3. Facebook/Instagram Ads

### Account Level
```
{url}?utm_source=facebook&utm_medium=paid_social&utm_campaign={{campaign.name}}&utm_content={{adset.name}}&utm_term={{ad.name}}&fbclid={{fbclid}}&platform={{platform}}&placement={{placement}}&device={{device_platform}}
```

### Campaign Level
```
{url}?utm_source=facebook&utm_medium=paid_social&utm_campaign={{campaign.id}}_{{campaign.name}}&utm_content={{adset.name}}&placement={{placement}}&platform={{platform}}&fbclid={{fbclid}}
```

### Ad Set Level
```
{url}?utm_source=facebook&utm_medium=paid_social&utm_campaign={{campaign.name}}&utm_adset={{adset.id}}&utm_content={{ad.name}}&audience={{adset.targeting}}&placement={{placement}}&fbclid={{fbclid}}
```

## 4. TikTok Ads

### Account Level
```
{landing_page_url}?utm_source=tiktok&utm_medium=paid_social&utm_campaign={campaign_name}&utm_content={adgroup_name}&ttclid={ttclid}&device={device_model}&creative={creative_id}
```

### Campaign Level
```
{landing_page_url}?utm_source=tiktok&utm_medium=paid_social&utm_campaign={campaign_id}&campaign_name={campaign_name}&adgroup={adgroup_name}&ttclid={ttclid}
```

### Ad Group Level
```
{landing_page_url}?utm_source=tiktok&utm_medium=paid_social&utm_campaign={campaign_name}&adgroup_id={adgroup_id}&creative={creative_id}&ttclid={ttclid}
```

## 5. LinkedIn Ads

### Account Level
```
{lpurl}?utm_source=linkedin&utm_medium=paid_social&utm_campaign={campaignname}&utm_content={creative}&campaign_id={campaignid}&creative_id={creativeid}&placement={placement}&linkedin_id={linkedin_id}
```

### Campaign Level
```
{lpurl}?utm_source=linkedin&utm_medium=paid_social&utm_campaign={campaignname}&campaign_id={campaignid}&placement={placement}&audience={audience}&linkedin_id={linkedin_id}
```

### Ad Level
```
{lpurl}?utm_source=linkedin&utm_medium=paid_social&utm_campaign={campaignname}&ad_id={creative}&placement={placement}&linkedin_id={linkedin_id}
```

## 6. Outbrain

### Campaign Level
```
{clickurl}?utm_source=outbrain&utm_medium=discovery&utm_campaign={campaign_name}&utm_content={section_name}&campaign_id={campaign_id}&publisher={publisher}&section={section_name}&ob_click_id={ob_click_id}
```

### Ad Level
```
{clickurl}?utm_source=outbrain&utm_medium=discovery&utm_campaign={campaign_name}&utm_content={ad_title}&publisher={publisher}&section={section_name}&ob_click_id={ob_click_id}
```

## Implementation Guide

### Step 1: Preparation
1. Document your current URL structure
2. List all required tracking parameters
3. Set up URL builder spreadsheet
4. Test URL character length (keep under 2048 characters)

### Step 2: Platform-Specific Setup

#### Google Ads:
1. Navigate to Account Settings
2. Select Tracking Templates
3. Insert appropriate template
4. Test using Preview Tool
5. Implement at desired level

#### Microsoft Ads:
1. Go to Campaign Settings
2. Add URL Options
3. Insert tracking template
4. Enable auto-tagging
5. Test using UET tag

#### Facebook Ads:
1. Access Ads Manager
2. Select URL Parameters
3. Add dynamic parameters
4. Enable Facebook pixel
5. Test event tracking

#### TikTok Ads:
1. Open Campaign Settings
2. Add URL Parameters
3. Enable TikTok pixel
4. Test click tracking
5. Verify parameter passing

### Step 3: Validation
1. Use Preview Tools
2. Check Parameter Passing
3. Verify Analytics Reception
4. Test Cross-Device Tracking
5. Monitor First 24 Hours

### Step 4: Analytics Setup
1. Set up Custom Reports
2. Create UTM Filters
3. Set up Conversion Goals
4. Configure Channel Groupings
5. Test Data Collection

### Best Practices:
1. Use Consistent Naming:
   - All lowercase
   - No spaces (use underscores)
   - Consistent UTM parameters

2. Platform-Specific:
   - Google: Always include gclid
   - Bing: Always include msclkid
   - Facebook: Use dynamic parameters
   - TikTok: Include ttclid

3. Maintenance:
   - Monthly URL audit
   - Regular QA checks
   - Update documentation
   - Monitor character length

### Common Issues and Solutions:

1. Parameter Not Tracking:
   - Check case sensitivity
   - Verify parameter format
   - Test URL encoding

2. Data Not Showing:
   - Check analytics filters
   - Verify tag firing
   - Check parameter mapping

3. URL Too Long:
   - Shorten parameter names
   - Remove unnecessary parameters
   - Use URL shortener if needed

### Security Considerations:
1. Avoid PII in URLs
2. Use HTTPS
3. Implement URL encoding
4. Regular security audits
5. Monitor for parameter tampering

### Reporting Setup:
1. Create Custom Reports
2. Set up Automated Alerts
3. Configure Dashboard
4. Schedule Regular Exports
5. Set up Cross-Platform Attribution
