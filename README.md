# fastapi-codegen-finetune

This project implements code completion for FastAPI framework by fine-tuning the CodeGen-mono-small model using Low-Rank Adaptation (LoRA).

## Project Challenges and Limitations

The project faced several practical constraints:
- Limited computational resources (no dedicated GPU available)
- Google Colab stability issues affecting training sessions
- Time constraints due to academic commitments

Despite these challenges, the project successfully demonstrated the effectiveness of parameter-efficient fine-tuning techniques for code completion tasks. The scope was intentionally focused to ensure meaningful results could be achieved within the available resources.

## Data and Model Details
- **Base Model**: CodeGen-mono-small (350M parameters)
- **Fine-tuning**: LoRA (rank: 4, alpha: 32)
- **Data**: ~2000 FastAPI code snippets from official documentation
- **Split**: 80/10/10 (train/val/test)

## Data Sources & References
- [Long Code Arena](https://arxiv.org/abs/2406.11612) - Benchmarking methodology
- [CodeGen](https://github.com/salesforce/CodeGen) - Base model (350M parameters)
- [FastAPI](https://fastapi.tiangolo.com/) - Source of training data

## Learning Curves
![Training and Validation Loss](images/loss.png)
![Grad Norm](images/grad_norm.png)

#### Analysis of Learning Curves
The model training shows several interesting patterns:
1. **Initial Phase**:
   - Rapid decrease in training loss
   - Validation loss follows training loss closely
   - Quick improvement in target accuracy

2. **Middle Phase**:
   - Learning rate adjustments help maintain steady progress
   - Gradual improvement in validation metrics
   - Target accuracy continues to improve but at a slower rate

3. **Final Phase**:
   - Model converges to stable performance
   - Validation loss stabilizes
   - No signs of overfitting (training and validation losses remain close)

The learning curves demonstrate that our LoRA fine-tuning approach successfully adapted the CodeGen model to FastAPI code completion tasks, achieving a significant reduction in validation loss while maintaining good generalization.

## Future Improvements
1. Expand training data with more diverse FastAPI examples
2. Experiment with different LoRA configurations
3. Implement better evaluation metrics for code quality
4. Experiment with QLoRA - unfortunately I had technical problems :-(
