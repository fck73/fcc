def main():
    # 示例文本 - 产品评论
    review = """
    I absolutely love this product! The build quality is exceptional 
    and it works flawlessly. The customer service was also top-notch - 
    they resolved my issue within minutes. Highly recommended!
    """
    
    print("Original Text:")
    print(review)
    print("\n" + "="*50 + "\n")
    
    # 分析情感
    polarity, subjectivity = analyze_sentiment(review)
    print(f"Sentiment Analysis - Polarity: {polarity:.2f}, Subjectivity: {subjectivity:.2f}")
    print("\nInterpretation:")
    if polarity > 0.5:
        print("➔ Strongly Positive Review")
    elif polarity > 0:
        print("➔ Positive Review")
    elif polarity == 0:
        print("➔ Neutral Review")
    elif polarity > -0.5:
        print("➔ Negative Review")
    else:
        print("➔ Strongly Negative Review")
    print("\n" + "="*50 + "\n")
    
    # 词汇分析
    pos_counts, word_counts = get_word_stats(review)
    
    # 可视化
    visualize_results(polarity, subjectivity, pos_counts, word_counts)

if __name__ == "__main__":
    main()
