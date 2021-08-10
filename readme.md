# How to use

```
import {formik, form} from 'formik'
import \* as Yup from 'yup'
import FormikControl from '../Formik/FormikControl'

const validationSchema = Yup.object({
nis: Yup.number()
.required('NIS diperlukan')
.test('is-10', 'Harus memiliki 10 character', (value) => {
if (!isNaN(value)) {
return value.toString().length === 10
}
}),
nisn: Yup.number()
.required('NISN diperlukan')
.test('is-10', 'Harus memiliki 10 character', (value) => {
if (!isNaN(value)) {
return value.toString().length === 10
}
}),
name: Yup.string().required('Nama diperlukan'),
gender: Yup.string().required('Jenis kelamin diperlukan'),
year_of_entry: Yup.string().required('Tahun ajaran diperlukan'),
email: Yup.string()
.required('Email diperlukan')
.email('Email tidak valid'),
})

<Formik
initialValues={{
      nis: student.nis || '',
      nisn: student.nisn || '',
      name: student.name || '',
      gender: student.gender || '',
      phone_number: student.phone_number || '',
      year_of_entry: student.year_of_entry || '',
      email: student.email || '',
   }}
validationSchema={validationSchema}
onSubmit={submitHandler}

> {(props) => (

      <Form>
         <Stack spacing={5}>
            <FormikControl
               name='nis'
               control='input'
               label='NIS'
               type='number'
               placeholder='Masukan 10 character NIS'
               color='secondary'
               fontWeight='400'
               error={errors}
               required={true}
            />

            <FormikControl
               name='nisn'
               control='input'
               label='NISN'
               type='number'
               placeholder='Masukan 10 character NISN'
               color='secondary'
               fontWeight='400'
               required={true}
            />
            <FormikControl
               name='name'
               control='input'
               label='Nama'
               placeholder='Masukan nama anda'
               color='secondary'
               fontWeight='400'
               required={true}
            />
            <FormikControl
               name='email'
               control='input'
               label='Email'
               placeholder='Masukan nama anda'
               color='secondary'
               fontWeight='400'
               type='email'
               required={true}
            />
            <FormikControl
               name='phone_number'
               control='input'
               label='Nomor Telepon'
               placeholder='Masukan nomor telepon'
               color='secondary'
               fontWeight='400'
               type='number'
            />
            <FormikControl
               name='gender'
               control='radio'
               label='Jenis Kelamin'
               required={true}
               values={[
                  { value: 'L', name: 'Laki-laki' },
                  { value: 'P', name: 'Perempuan' },
               ]}
            />
            <FormikControl
               name='year_of_entry'
               control='select'
               label='Tahun Ajaran'
               placeholder='Pilih tahun ajaran'
               color='secondary'
               fontWeight='400'
               required={true}
               options={[
                  {
                     key: 0,
                     name: '2021/2022',
                     value: '2021/2022',
                  },
                  {
                     key: 1,
                     name: '2022/2023',
                     value: '2022/2023',
                  },

                  {
                     key: 2,
                     name: '2023/2024',
                     value: '2023/2024',
                  },
                  {
                     key: 3,
                     name: '2024/2025',
                     value: '2024/2025',
                  },
                  {
                     key: 4,
                     name: '2025/2026',
                     value: '2025/2026',
                  },
                  {
                     key: 5,
                     name: '2026/2027',
                     value: '2026/2027',
                  },
                  {
                     key: 6,
                     name: '2027/2028',
                     value: '2027/2028',
                  },
                  {
                     key: 7,
                     name: '2028/2029',
                     value: '2028/2029',
                  },
                  {
                     key: 8,
                     name: '2029/2030',
                     value: '2029/2030',
                  },
                  {
                     key: 9,
                     name: '2030/2031',
                     value: '2030/2031',
                  },
               ]}
            />

            <Flex justifyContent='flex-end'>
               <Button
                  bg='#111'
                  variant='solid'
                  color='white'
                  _hover={{
                     backgroundColor: 'secondary',
                  }}
                  _focus={{
                     outline: 'none',
                  }}
                  isLoading={props.isSubmitting}
                  type='submit'
               >
                  Submit
               </Button>
            </Flex>
         </Stack>
      </Form>

)}
</Formik>
```
