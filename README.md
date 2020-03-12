# CitaNZ's Image Cropper
It's a continious development of Salted Herring's Cropper Field for SilverStripe - 4 (https://github.com/salted-herring/salted-cropper)

### Usage
1. Install
  ```
  composer require cita/image-cropper
  ```

2. /dev/build?flush=all

3. Sample code:

    ```php
    ...
    use Cita\ImageCropper\Model\CitaCroppableImage;
    use Cita\ImageCropper\Fields\CroppableImageField;
    ...
    private static $has_one = array(
        'Photo'     =>  CitaCroppableImage::class
    );


    public function getCMSFields()
    {
        $fields = parent::getCMSFields();
        ...
        // adding a free cropper
        $fields->addFieldToTab(TAB_NAME, CroppableImageField::create('PhotoID', A_TITLE_TO_THE_FILED);

        // adding cropper with ratio
        $fields->addFieldToTab(TAB_NAME, CroppableImageField::create('PhotoID', A_TITLE_TO_THE_FILED)->setCropperRatio(16/9));
        ...
        return $fields;        
    }

    ```

4. Add image > upload/select > save > edit > do your cropping > save

5. Output
    ```html
    $Photo
    $Photo.Cropped
    $Photo.Cropped.SetWidth(100)
    ```
