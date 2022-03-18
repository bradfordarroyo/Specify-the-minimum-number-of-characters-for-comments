# Specify-the-minimum-number-of-characters-for-comments
Specify the minimum number of characters for comments
/ Requires a minimum length of a comment
add_filter('preprocess_comment', 'minimal_comment_length');
function minimal_comment_length($commentdata)
{
    $minimalCommentLength = 70;
    if (strlen(trim($commentdata['comment_content'])) < $minimalCommentLength) {
        wp_die('All comments must be at least ' . $minimalCommentLength . ' characters long.');
    }
    return $commentdata;
}
