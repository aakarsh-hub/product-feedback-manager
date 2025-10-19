# Product Feedback Manager

A centralized platform for collecting, analyzing, and acting on user feedback.

## Purpose

This platform helps product teams systematically gather user feedback from multiple channels, analyze trends and sentiments, and convert insights into actionable product improvements. It bridges the gap between users and product development teams.

## Main Features

- **Multi-Channel Collection**: Capture feedback from email, in-app widgets, surveys, and social media
- **Smart Categorization**: AI-powered automatic tagging and categorization of feedback
- **Sentiment Analysis**: Real-time sentiment scoring and trend detection
- **User Impact Scoring**: Prioritize feedback based on user segments and revenue impact
- **Feedback Boards**: Public roadmap and voting system for transparency
- **Integration Hub**: Connect with CRM, support ticketing, and development tools
- **Analytics Dashboard**: Visualize feedback trends, themes, and feature requests
- **Closing the Loop**: Automated notifications when feedback is addressed

## Sample Usage

```python
from feedback_manager import FeedbackClient

# Initialize the client
fm = FeedbackClient(api_key='your-api-key')

# Submit feedback from your application
feedback = fm.submit_feedback(
    user_id='user123',
    source='in-app',
    category='feature_request',
    content='Would love to see dark mode support',
    metadata={'plan': 'premium', 'mrr': 99}
)

# Analyze feedback sentiment
sentiment = fm.analyze_sentiment(feedback.id)
print(f"Sentiment: {sentiment.score} ({sentiment.label})") 
# Output: Sentiment: 0.85 (positive)

# Get top feature requests
top_requests = fm.get_feature_requests(
    timeframe='last_30_days',
    min_votes=10,
    status='under_review'
)

for request in top_requests:
    print(f"{request.title}: {request.votes} votes")
    print(f"Impact Score: {request.impact_score}")

# Create product roadmap item from feedback
roadmap_item = fm.create_roadmap_item(
    feedback_ids=[feedback.id],
    title='Dark Mode Support',
    status='planned',
    target_quarter='Q1 2026'
)

# Notify users when feature is released
fm.close_feedback_loop(
    roadmap_item_id=roadmap_item.id,
    release_notes='Dark mode is now available in Settings'
)
```

## Quick Start

1. Install: `pip install product-feedback-manager`
2. Configure your API key and organization settings
3. Add feedback collection widgets to your application
4. Set up automated categorization rules
5. Create your public feedback board and roadmap
6. Monitor analytics dashboard for insights

## Benefits for Product Management

- **Customer-Centric Development**: Build what users actually need
- **Reduced Churn**: Address pain points before users leave
- **Prioritization Data**: Make decisions based on user impact
- **Stakeholder Alignment**: Share quantified user needs with leadership
- **Competitive Intelligence**: Track feature parity with competitors
