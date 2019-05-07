# Simple neural style transfer (Tensorflow)

Based on (Gatys et al., 2015) idea. Trick with shifting Gram matrices from (Novak et al., 2016) is used.
Since Tensorflow doesn’t have ready L-BFGS optimisation (which is recommended in the paper), I’ve used Adam optimiser with following parameters:
1. beta1 = 0.99.
2. Learning rate = 8.
3. Epsilon = 1e-1.

### Example
<table><tr>
    <td>My cat
<img src='/content/cat.jpg'>
    </td>
    <td>
Combined with E.Munch 'Scream'
<img src='/style/scream.jpg'>
    </td>
    <td>
Gives
<img src='/output/cat+scream.png'>
    </td>
</tr></table>

### Crucial notes:
1. 1000 iterations are usually enough to get visually appealing results.
2. Empirically found that best style_loss/content_loss ratio is 1e3.
3. Algorithm works worse on style images with sharp lines and ripple.
4. It’s better to start from content image (not a white noise) when optimising.

### Project structure
All code is in the Jupyter notebook.

`content` - content images<br>
`style` - style images<br>
`output` - results


P.S. My computer is pretty old so Tensorflow works as fast as a drunk turtle. That is why optimisation was done via Google Colaboratory.
